---
layout: about
title: about
permalink: /

profile:
  align: right
  image: prof_pic.jpg
  image_circular: true # crops the image to a circle

selected_papers: false # the publication list below is rendered inline, so it can sit between the sections
social: false # contact links are shown beside the introduction instead

announcements:
  enabled: false # enable once there is real news to report (see _news/)

latest_posts:
  enabled: false # no blog on this site
---

{% include site-extras.html %}

I am a Ph.D. student at the College of Computer Science and Artificial Intelligence, Fudan
University. My research interests lie in <strong>Brain-Inspired Computing and Intelligence</strong>,
with a focus on <strong>Spiking Neural Networks</strong> and <strong>Embodied Intelligence</strong>.

I am still exploring the research questions I wish to pursue in the long term, and I would be
delighted to connect with researchers who share these interests and can offer guidance,
mentorship, or opportunities for collaboration.

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
</div>

## Selected Publications

<div class="publications">
{% bibliography --group_by none --query @*[selected=true]* %}
</div>

## Current Research

<div class="current-research-feature">
  <div class="current-research-copy">
    <p>I am exploring <strong>event-lifecycle memory</strong> for long-horizon embodied
    intelligence: how agents can identify, preserve, and retrieve task-relevant evidence
    after it is no longer visible in the current observation.</p>
  </div>
  <div class="current-research-media">
    {% include figure.liquid path="/assets/img/event_memory.jpg" class="current-research-image rounded z-depth-1" zoomable=true alt="Conceptual illustration of event-lifecycle memory for long-horizon embodied intelligence" %}
    <p class="figure-caption">An event-lifecycle memory preserves task-relevant evidence across interaction.</p>
  </div>
</div>
