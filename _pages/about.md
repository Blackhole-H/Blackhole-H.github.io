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

## Research Interests

<div class="research-card">
  <p>
    My research interests lie in <strong>Brain-Inspired Computing and Intelligence</strong>.
    Inspired by the remarkable efficiency and intelligence of biological brains, I aspire to
    develop AI systems that are not only computationally efficient but also capable of more
    flexible and adaptive intelligence.
  </p>
  <p>
    My previous research has focused on <strong>Spiking Neural Networks (SNNs)</strong>, where
    I explore novel neuron models and neural architectures to enhance their computational and
    representational capabilities.
  </p>
  <p>
    More recently, I have been extending my interests toward <strong>Embodied Intelligence</strong>,
    exploring how principles of biological intelligence can inspire new approaches to artificial
    intelligence.
  </p>
  <p>
    I am still exploring the research questions I wish to pursue in the long term, and I would
    be delighted to connect with researchers who share these interests and can offer guidance,
    mentorship, or opportunities for collaboration.
  </p>
</div>

## Selected Publications

<div class="publications">
{% bibliography --group_by none --query @*[selected=true]* %}
</div>

## Current Research

### Event-Lifecycle Memory for Long-Horizon Embodied Intelligence

Long-horizon embodied tasks often require agents to make decisions based on past
interactions, even when critical information is no longer visible in the current
observation. I am exploring **event-lifecycle memory**, with a focus on how
embodied agents can identify, preserve, and utilize task-relevant information
throughout extended interactions. Rather than treating historical observations
as isolated snapshots, I am interested in understanding how meaningful events
unfold over time and how their associated evidence can support future decisions.
My goal is to develop efficient and adaptive memory mechanisms that enable more
reliable long-horizon embodied intelligence.

{% include figure.liquid path="/assets/img/event_memory.jpg" class="img-fluid rounded z-depth-1" zoomable=true alt="Conceptual illustration of event-lifecycle memory for long-horizon embodied intelligence" %}
