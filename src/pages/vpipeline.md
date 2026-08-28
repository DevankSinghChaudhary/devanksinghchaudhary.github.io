---
layout: ../layouts/MarkdownPage.astro
title: VPipeline
description: Autonomous Video Creation Pipeline
---
<div class="meaning">
  <img src="/projects/vpipeline.png" alt="Logo of VPipeline Project">
</div>
  
VPipeline is the ultimate project I'm working on right now!  
To understand why? Understand VPipeline.

---

# VPipeline

The main function of this project is to automate the video creation process.  
Read it right creation, not just editing.  
  
From Research to Speech to .mp4 everything automated.  
In the previous version of this project [[v1-Github](https://github.com/devanksinghchaudhary/video-creation-pipeline)]. I actually reached till `.mp4` output.  
But it's architecture or structure was too weak.  
  
I had two options either patch the whole version 1 or start from scratch.  
I chose option 2, which might seem bad option but if you are developer go see [version 1](https://github.com/devanksinghchaudhary/video-creation-pipeline) it was poorly structured.  
Patching it could cost me more time than starting from scratch.  
  
## How VPipeline Works?  
`This is technical section. You could skip this entierly to` [The Core Idea](#the-core-idea)
  
<div class="image-container">
  <img
    src="/projects/vpipeline-structure.png"
    alt="Structure of VPipeline"
    onclick="this.parentElement.classList.toggle('open')"
  />
</div>
  
This is rough structure of VPipeline.  
These are the major nodes in the pipeline  
  
### Research

The system first researches the given topic and produces structured information that can be used later by the pipeline.

The important part here is that research isn't just there to give the AI some context. It becomes an actual input for the next stage.

### Script

The research is then turned into a documentary script.

The goal isn't simply to generate paragraphs. The script needs to work as narration, which means structure, pacing and transitions matter.

### TTS Formatting

The script is prepared for text-to-speech.

This stage exists separately because the text that reads well on a screen isn't necessarily the text that should be passed directly to a TTS engine.

### Audio

The formatted script is converted into narration.

The resulting audio becomes one of the most important pieces of the timeline because the visuals eventually need to follow what is actually being said.

### Visual Planning

Now the pipeline has to answer a different question:

`What should the viewer see while this is being said?`

The narration is broken down into visual requirements rather than simply throwing random relevant images at it.

### Asset Search

The system searches for the assets required by the visual plan.

This can include images, footage and other visual material depending on what the scene requires.

### Asset Sorting

Finding assets isn't enough.

There can be multiple possible assets for the same visual requirement, along with irrelevant or redundant results.

This stage exists to filter and organize them before they reach composition.

### Visual Decomposition

The narration is further broken down into individual visual units.

A single sentence might require multiple visuals, while another might need to remain on screen for much longer.

This is where the relationship between narration and visuals becomes much more explicit.

### Composition

The selected assets are turned into actual scenes.

Positioning, timing, text, transitions and other visual elements are composed programmatically.

### Render

Finally, everything is rendered into the actual video.

The goal is to reach a finished `.mp4` without requiring me to manually assemble every scene in a video editor.


## The Core Idea

VPipeline isn't meant to be:

`prompt → video`

That's too simple a way to think about documentary creation.

A documentary has multiple independent problems:

Research has to be accurate.  
The script has to make sense.  
The narration has to sound natural.  
The visuals have to correspond to what is being said.  
Assets shouldn't constantly repeat.  
And everything eventually has to fit together on an actual timeline.  
So instead of asking one AI system to do everything, VPipeline separates the problems.  
**Research → Script → TTS → Audio → Visual Planning → Assets → Composition → Render**  
Each stage has its own responsibility and produces structured output for the next stage.


## Why VPipeline?

This is probably the most important part of the project.

I don't want AI to randomly generate a video and call it done.

I want AI to handle the parts that require reasoning.

What should be researched?

What should be said?

What should be shown?

How should the narration be divided?

What visual would actually make sense here?

Then software handles the parts that should be deterministic.

Audio processing.

Timing.

Asset management.

Composition.

Synchronization.

Rendering.

That separation is what I'm actually trying to build with VPipeline.


## What Makes It Different?

The interesting part isn't that AI is involved.

Almost every modern video-generation system uses AI somewhere.

The interesting part is **how the work is divided**.

Instead of treating the entire documentary as one generation task, VPipeline treats it as a production system.

If something goes wrong during research, I should be able to fix the research without rebuilding everything.

If the visual selection is bad, I should be able to improve that stage without rewriting the documentary.

If rendering fails, the editorial decisions should still exist as structured data.

That's why the pipeline exists.


## What I'm Optimizing For

- Factual accuracy
- Natural narration
- Relevant visuals
- Low asset redundancy
- Audio-driven timing
- Reproducible rendering
- Minimal manual editing

The goal isn't just to make video generation possible.

It's to make the process **structured enough that it can actually be improved**.


## Current State

VPipeline is still under active development.

The architecture is changing as I encounter problems during actual production.

Some parts are already working. Others are being rebuilt or experimented with.

I'm less interested in making a demo that works once and more interested in building a system that can repeatedly produce documentaries without falling apart as complexity increases.


## What's Next?

There is still a lot to solve.

Better visual selection.

Better synchronization between narration and visuals.

More intelligent asset handling.

Better scene composition.

Faster rendering.

And eventually, reducing the amount of manual intervention required even further.

VPipeline isn't finished.

That's kind of the point.
