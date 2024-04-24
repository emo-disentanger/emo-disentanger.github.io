---
layout: home
title: EMO-Disentanger
description: Emotion-driven Piano Music Generation via Two-stage Disentanglement and Functional Representation
---

## Introduction

In this paper, we employ a **two-stage Transformer-based model** on emotion-driven piano performance generation. The first stage focuses on **valence modeling** via lead sheet composition, while the second stage addresses **arousal modeling** by introducing performance-level attributes.

<div align="center">
  <img src="figures/model.png" width=1000 alt="">
  <figcaption><strong>Fig.1</strong> The two-stage framework of emotion-driven piano performance generation.</figcaption>
</div>

We also propose a novel **functional representation** for symbolic music, encoding both melody and chords with Roman numerals relative to musical keys, to consider the interactions among notes, chords and tonalities. 

<div align="center">
  <img src="figures/representation.png" width=500 alt="">
  <figcaption><strong>Fig.1</strong> Illustration of (a) [REMI](https://github.com/YatingMusic/remi) and (b) the proposed functional representation, differing in note pitch and chord name events.</figcaption>
</div>

<div align="center">
  <img src="figures/switch.png" width=400 alt="">
  <figcaption><strong>Fig.3</strong> The conversion between letters and Roman numerals in the cases of C major and c minor scales. Solid arrows denote strict one-to-one conversions, and dotted arrows denote optional one-to-either conversions.</figcaption>
</div>

This new method takes **musical keys** into account, recognizing their significant role in shaping valence perception through major-minor tonality. 

<div align="center">
  <img src="figures/key_distribution.png" width=500 alt="">
  <figcaption><strong>Fig.2</strong> Key histogram of high/low valence clips from the emotion-labeled piano music dataset EMOPIA</figcaption>
</div>

Experiments demonstrate the effectiveness of our framework and representation on emotion modeling. Additionally, our method enables new capabilities to control the arousal levels of generation under the same lead sheet, leading to more flexiable emotion controls.



[jekyll-organization]: https://github.com/jekyll
