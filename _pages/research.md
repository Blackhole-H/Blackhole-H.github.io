---
layout: page
permalink: /research/
title: research
description: Brain-inspired computing with spiking neural networks, and long-horizon memory for embodied agents.
nav: true
nav_order: 3
---

{% include site-extras.html %}

My work follows a loose trajectory: efficient neural computation, then the
representations that make that computation worthwhile, then the memory and behavior
such representations can support. The two areas below describe where I currently
spend most of my time.

## Research Area 1 — Brain-Inspired Computing

Dense neural computation is expensive, and much of that expense is spent
communicating values that carry little information. Spiking neural networks offer a
different accounting: units exchange sparse, discrete events, and synaptic
integration reduces largely to accumulation. That makes them a natural place to ask
how much computation a task actually requires.

My work in this area is less about scaling spiking models up than about
understanding what they are good at, and about keeping them efficient — in the number
of timesteps, the amount of cross-channel communication, and the precision of the
values they carry.

### Representative work

<p><strong>SpikeLite: Lightweight Spiking Neural Networks for Time-Series Forecasting</strong><br>
Bang Hu, Changze Lv, Mingjie Li, Xiaoqing Zheng, Wei Cao, Fan Zhang.<br>
Built around a frequency-selective spiking encoder and a sparse spiking channel
attention module, with a lighter channel-independent path for cases where explicit
channel interaction is not needed.<br>
<a href="https://arxiv.org/abs/2609.35097">arXiv:2609.35097</a></p>

<p><strong>QuantaSpike: Short-Window Spike-Driven Quantization for Large Language Models</strong><br>
Bang Hu, Guowei Zhu, Changze Lv, Xiaoqing Zheng, Fengzhe Zhang, Fan Zhang, Wei Cao.<br>
Applies spike-driven computation to quantized LLMs through logarithmic ternary
integrate-and-fire neurons, group-adaptive gain, and selective outlier admission,
under a short firing window.<br>
<a href="https://arxiv.org/abs/2609.34259">arXiv:2609.34259</a></p>

<p><strong>SpikeSTAG: A Dendritic Compartmental Spiking Graph Network for Multivariate Time-Series Forecasting</strong><br>
Bang Hu, Changze Lv, Mingjie Li, Yunpeng Liu, Xiaoqing Zheng, Fengzhe Zhang, Wei Cao, Fan Zhang.<br>
Integrates graph structural learning with spike-based temporal processing for
multivariate time-series forecasting, without requiring a predefined graph.<br>
Accepted at NeurIPS 2026.<br>
<a href="https://arxiv.org/abs/2508.02069">arXiv:2508.02069</a></p>

## Research Area 2 — Embodied Intelligence

### A. Long-Horizon Memory for Embodied Agents

An embodied agent operating over a long horizon observes far more than it can keep.
Storage is not the only constraint: retaining everything makes retrieval harder, and
most of what is retained will never matter again. The interesting problem is therefore
selection — deciding what deserves to be remembered — together with the representation
that lets a remembered moment stay useful.

Questions I am working on:

<ul class="research-questions">
  <li>What makes a frame informative for future decisions?</li>
  <li>How can important events be identified over long horizons?</li>
  <li>How should an agent retrieve relevant visual memories, and what representation makes retrieval reliable?</li>
  <li>How can memory be organized so that the cost of keeping it stays bounded as the horizon grows?</li>
</ul>

This covers keyframe detection and selection, event-aware memory representations,
long-horizon visual memory, and memory retrieval and utilization.

### B. Biological Inspiration from the <em>Drosophila</em> Brain

Biological nervous systems solve perception, memory, and action under constraints
that no engineered system currently respects: very few neurons, very little energy,
and no separation between remembering and acting. The <em>Drosophila</em> brain, whose
circuitry is increasingly well mapped, is a useful scale at which to read those
solutions off directly.

I am interested in what such circuits suggest for embodied intelligence — how
sensorimotor processing is organized, how memory and action are coupled, and which of
these principles transfer into models.

<p class="research-note">
  This is an exploratory interest rather than a completed line of work. I have no
  results, papers, or systems on biological circuit reconstruction to report yet.
</p>
