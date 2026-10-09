---
layout: about
title: about
permalink: /
subtitle: >-
  PhD Student, College of Computer Science and Artificial Intelligence, Fudan University
  <br>Brain-Inspired Computing &amp; Embodied Intelligence

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular

selected_papers: false # the publication list below is rendered inline, so it can sit between the sections
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # enable once there is real news to report (see _news/)

latest_posts:
  enabled: false # no blog on this site
---

{% include site-extras.html %}

I am a PhD student at the College of Computer Science and Artificial Intelligence,
Fudan University. My research lies in brain-inspired computing and embodied
intelligence.

Much of my current work concerns efficient neural computation with
**spiking neural networks** — models that exchange discrete events instead of
dense values. I am interested in what such models can represent, how cheaply they
can represent it, and where the inductive bias of spike-based computation actually
helps. This line of work includes **SpikeSTAG**, which combines graph structural
learning with spike-based temporal processing for multivariate time-series
forecasting; **SpikeLite**, which keeps spiking forecasters lightweight through
frequency-selective encoding and sparse cross-channel interaction; and
**QuantaSpike**, which applies short-window spike-driven computation to quantized
large language models.

More recently, I have been thinking about what comes after perception: **memory**.
An embodied agent acting over a long horizon cannot retain everything it observes,
so the question of what is worth keeping becomes as important as how observations
are encoded in the first place.

## Research Interests

<div class="research-grid">
  <div class="research-card">
    <h3>Brain-Inspired Computing</h3>
    <span class="research-card-rule"></span>
    <p>
      I study spiking neural networks as a substrate for efficient computation,
      together with the representations that make them effective: temporal and
      spatio-temporal structure, spectral decomposition, and low-timestep
      encodings that compress information into few events.
    </p>
    <p>
      This work is motivated by a simple question — how much of what a network
      computes is actually needed, and how much of the remainder can be removed
      before accuracy starts to matter.
    </p>
  </div>
  <div class="research-card">
    <h3>Embodied Intelligence</h3>
    <span class="research-card-rule"></span>
    <p>
      I am interested in long-horizon memory for embodied agents: identifying the
      moments in a long interaction that remain useful later, retaining them in a
      compact form, and retrieving them when a decision depends on them.
    </p>
    <p>
      I am also drawn to biological neural circuits, in particular those of the
      <em>Drosophila</em> brain, as a source of principles for organizing
      perception, memory, and action in small systems.
    </p>
  </div>
</div>

## Selected Publications

<div class="publications">
{% bibliography --group_by none --query @*[selected=true]* %}
</div>

## Current Research

**Long-Horizon Memory for Embodied Agents.** An agent interacting with the world
over an extended period accumulates far more observation than it can store, and
most of that observation is irrelevant to any future decision. I am interested in
how such an agent should decide which moments to keep, how those moments should be
represented so that they stay useful rather than merely present, and how the right
memory is retrieved when a decision depends on it. Concretely, this covers
keyframe detection and selection, event-aware memory representations, long-horizon
visual memory, memory retrieval and utilization, and memory organizations that stay
within a realistic budget.

<p class="research-note">
  This work is in progress. Results, papers, and systems will be listed here and on
  the <a href="/publications/">publications page</a> as they become available.
</p>
