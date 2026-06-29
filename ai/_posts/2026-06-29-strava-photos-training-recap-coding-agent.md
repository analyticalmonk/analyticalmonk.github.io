---
layout:     post
title:      Turning Strava data and gym photos into a training recap with my coding agent
comments:   true
image:      /assets/img/strava_infographic_post_header.png
description: >
  Strava’s metrics alone couldn’t tell the story of my training, because important context lived in photos of my gym’s whiteboard. Here’s how I combined Strava data with a coding agent’s vision layer to build a half-year-in-review infographic.
categories: [ai]
---

This has been a good year so far with respect to my workouts and running routine. That’s why I wanted a nice half-year-in-review infographic. That’s all.

This is a quick story, not so much a tutorial, of how I got what I wanted using Strava and my coding agent. Here is what the final infographic looked like:

<p style="text-align: center;">
  <img src="/assets/img/strava-recap-infographic.png" alt="Half-year training recap infographic titled “How I trained in 2026, so far” with counts for strength, runs, mobility and swims, plus a training mix breakdown" style="width: 100%; max-width: 520px;" />
</p>

The fun part to getting to the above was that Strava’s numbers alone could not really tell this story.

## Data, gym board photos and a pipeline

I use Samsung Fit 3 to track my workouts and the Strava mobile app to track my runs. The fitness tracker data syncs with Strava app on a periodic basis. This means Strava has the obvious metadata: activity type (workout/run, distance, duration, elevation, dates).

But here’s the interesting bit. For most of my gym sessions, the workout routines are in photos I attach to my posts. They were photographs of the day’s workout routine from my gym’s board. Lazy, I know.
The board contains the actual session structure: movements, focus area, and the difference between a strength day, a mobility day, and something in between.

<p style="text-align: center;">
  <img src="/assets/img/strava-recap-gym-board.jpg" alt="A Strava post titled “Evening Weight Training” with a photo of a gym whiteboard listing the day’s power-phase workout" style="width: 100%; max-width: 420px;" />
</p>

Strava only knows that I did a workout. So part of the project became a small image extraction and parsing pipeline. The core idea is to combine Strava’s structured data with the image-based context I had been casually attaching to posts.

*Fetch Strava activities + photos -> local cache -> agent reads and processes gym-board photos -> JSON-based description -> HTML infographic -> PNG poster*

The above pipeline consists of a couple of simple Python scripts. If some photos were already downloaded, the relevant script skipped them. If an image had already been processed, it was not processed again. If one extracted workout looked wrong, I could delete just that JSON file and regenerate it.

## Using coding agent for the vision task

Claude Code’s image-reading ability acted as a convenient vision layer. A script downloads the Strava photos and then prints the list of images that still need an associated JSON. For each relevant gym-board photo, the agent writes a small JSON file describing the workout.

Something like:

```json
{
  "type": "workout",
  "exercises": [
    {
      "name": "Goblet squat",
      "sets": 4,
      "reps": "8-10",
      "weight": "24kg",
      "muscle_groups": ["legs"]
    }
  ],
  "notes": "optional"
}
```

For a personal project, this agent-in-the-loop workflow was fast and easy. Once a JSON description exists, that image is considered processed. This made the vision step resumable and easy to fix.

## A little classification goes a long way

My Strava activity labels were not perfectly consistent. Some strength sessions were tagged as “weight training” and others as generic “workouts”. Mobility sessions also sometimes showed up as “workouts”.

So the code uses a mix of Strava activity type, activity title, and the extracted photo data to decide whether something is strength, mobility, running, swimming, yoga, or something else. That was enough to make the final poster feel accurate without turning this into a more complex classification project.

## Trying out Strava MCP

I briefly tried using the recently released [Strava MCP server](https://press.strava.com/articles/strava-launches-mcp-connector) to see if it could replace the scripts. It could have been useful if we only required activity metadata, but not for this project since there was no way to fetch the photos.

## To sum up

This was a nice example of AI helping me do something I wouldn't have had the time to do earlier. You can find or build on top of the code here: [analyticalmonk/strava-reporting](https://github.com/analyticalmonk/strava-reporting/tree/master). The easiest way to build on it is probably to clone the repo, point your coding agent at the README, update the config, and let it help you shape the report around your own Strava data.

For me, the output was an infographic. For you, it could be a running year-in-review, a cycling summary, a race-prep log, or just a better-looking personal fitness recap.

I may set up a personalized fitness agent with local models next. Meanwhile, if you build on top of this project or have a fitness/health-related agent workflow, I’ll love to hear about it!

*Thanks to [Ankita](https://www.linkedin.com/in/ankitamathur10/) for reading the draft.*
