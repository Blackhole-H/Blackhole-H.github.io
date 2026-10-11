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
  image_circular: true # crops the image to a circle

selected_papers: false # the publication list below is rendered inline, so it can sit between the sections
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # enable once there is real news to report (see _news/)

latest_posts:
  enabled: false # no blog on this site
---

{% include site-extras.html %}

I am a Ph.D. student at the College of Computer Science and Artificial
Intelligence, Fudan University.

I have led first-author research on efficient spiking neural networks —
SpikeSTAG, SpikeLite, and QuantaSpike — with preprints available on arXiv
(see [Publications](/publications/)).

Please feel free to contact me via email: hub24@m.fudan.edu.cn.

<div class="intro-contact" aria-label="Contact and profile links">
  <a class="intro-contact-link intro-contact-primary" href="mailto:hub24@m.fudan.edu.cn">
    <i class="fa-solid fa-envelope" aria-hidden="true"></i>
    Email
  </a>
  <a class="intro-contact-link" href="https://github.com/Blackhole-H" target="_blank" rel="noopener">
    <i class="fa-brands fa-github" aria-hidden="true"></i>
    GitHub
  </a>
  <a class="intro-contact-link" href="https://orcid.org/0009-0005-4274-7588" target="_blank" rel="noopener">
    <i class="ai ai-orcid" aria-hidden="true"></i>
    ORCID
  </a>
</div>

## Research Interests

<div class="research-grid research-grid-home">
  <article class="research-card">
    <h3>Brain-Inspired Computing</h3>
    <span class="research-card-rule" aria-hidden="true"></span>
    <p>Building efficient and adaptive AI systems from principles of biological computation.</p>
    <ul>
      <li>Efficient neural computation</li>
      <li>Adaptive intelligence</li>
    </ul>
  </article>
  <article class="research-card">
    <h3>Spiking Neural Networks</h3>
    <span class="research-card-rule" aria-hidden="true"></span>
    <p>Exploring spike-based neurons and architectures for temporal data and language models.</p>
    <ul>
      <li>Time-series forecasting</li>
      <li>Spike-driven quantization</li>
    </ul>
  </article>
  <article class="research-card">
    <h3>Embodied Intelligence</h3>
    <span class="research-card-rule" aria-hidden="true"></span>
    <p>Studying how memory and biological inspiration can support reliable long-horizon agents.</p>
    <ul>
      <li>Event-lifecycle memory</li>
      <li>Long-horizon interaction</li>
    </ul>
  </article>
</div>

## Selected Publications

<div class="publications">
{% bibliography --group_by none --query @*[selected=true]* %}
</div>

## Current Research

### Event-Lifecycle Memory for Long-Horizon Embodied Intelligence

<div class="current-research-feature">
  <div class="current-research-copy">
    <p>Long-horizon embodied tasks often require agents to make decisions based on past
    interactions, even when critical information is no longer visible in the current
    observation. I am exploring <strong>event-lifecycle memory</strong>, with a focus on how
    embodied agents can identify, preserve, and utilize task-relevant information
    throughout extended interactions.</p>
    <p>Rather than treating historical observations as isolated snapshots, I am interested in
    understanding how meaningful events unfold over time and how their associated evidence
    can support future decisions. My goal is to develop efficient and adaptive memory
    mechanisms that enable more reliable long-horizon embodied intelligence.</p>
  </div>
  <div class="current-research-media">
    {% include figure.liquid path="/assets/img/event_memory.jpg" class="current-research-image rounded z-depth-1" zoomable=true alt="Conceptual illustration of event-lifecycle memory for long-horizon embodied intelligence" %}
    <p class="figure-caption">An event-lifecycle memory preserves task-relevant evidence across interaction.</p>
  </div>
</div>
