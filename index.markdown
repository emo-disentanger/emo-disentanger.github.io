---
layout: home
title: EMO_Disentanger
description: Emotion-driven Piano Music Generation via Two-stage Disentanglement and Functional Representation
---

## Introduction

In this paper, we propose a novel **functional representation** designed as an alternative to [REMI](https://github.com/YatingMusic/remi), 
a popular event representation that uses note pitch values and chord names to encode symbolic music.

<div align="center">
  <img src="../figures/emo_harmonizer/representation.png" width=500 alt="">
  <figcaption><strong>Fig.1</strong> Illustration of (a) REMI and (b) the proposed functional
representation, differing in note pitch and chord name events.</figcaption>
</div>

This new method takes **musical keys** into account, 
recognizing their significant role in shaping music’s emotional character through major-minor tonality. 

<div align="center">
  <img src="../figures/emo_harmonizer/key_distribution.png" width=500 alt="">
  <figcaption><strong>Fig.2</strong> Key histogram of high/low valence clips from EMOPIA.</figcaption>
</div>

Specifically, our method represents both melody notes and chords with Roman numerals relative to musical keys, 
a **functional format** considering the relationships between notes, chords and scales (major or minor). 

<div align="center">
  <img src="../figures/emo_harmonizer/switch.png" width=400 alt="">
  <figcaption><strong>Fig.3</strong> Illustration of the conversion between letters and Roman numerals in the cases of C major / c minor. The solid line represents a direct one-to-one conversion, while the dotted line stands for a random conversion to either one of them.</figcaption>
</div>

It also allows for melodic variation with respect to keys and addresses the problem of data scarcity for better emotion modeling. 

A Transformer is employed to harmonize key-adaptable melodies, allowing for keys determined in rule-based or model-based manner.

[jekyll-organization]: https://github.com/jekyll
