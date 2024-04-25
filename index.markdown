---
layout: home
title: EMO-Disentanger
description: Emotion-driven Piano Music Generation via Two-stage Disentanglement and Functional Representation
---

# Introduction

In this paper, we employ a **two-stage Transformer-based model** on emotion-driven piano performance generation, considering the inadequate emotion modeling through end-to-end paradigms in previous works. The first stage focuses on **valence modeling** via lead sheet (melody + chord) composition , while the second stage addresses **arousal modeling** by introducing performance-level attributes, such as articulation, tempo, and velocity. 

<div align="center">
  <img src="figures/model.png" width=800 alt="">
  <figcaption><strong>Fig.1</strong> The two-stage framework of emotion-driven piano performance generation.</figcaption>
</div>

To further capture features that shape emotional valence, we propose a novel **functional representation** for symbolic music, designed as an alternative to [REMI](https://github.com/YatingMusic/remi), a popular event representation that uses note pitch values and chord names to encode symbolic music.

<div align="center">
  <img src="figures/representation.png" width=500 alt="">
  <figcaption><strong>Fig.2</strong> Illustration of (a) REMI and (b) the proposed functional representation, differing in note pitch and chord name events.</figcaption>
</div>

This new method takes **musical keys** into account, recognizing their significant role in shaping valence perception through major-minor tonality. It encodes both melody and chords with Roman numerals relative to musical keys, to consider the interactions among notes, chords and tonalities. 

<div align="center">
  <img src="figures/key_distribution.png" width=500 alt="">
  <figcaption><strong>Fig.3</strong> Key histogram of high/low valence clips from the emotion-labeled piano music dataset EMOPIA</figcaption>
</div>

<div align="center">
  <img src="figures/switch.png" width=400 alt="">
  <figcaption><strong>Fig.4</strong> The conversion between letters and Roman numerals in the cases of C major and c minor scales. Solid arrows denote strict one-to-one conversions, and dotted arrows denote optional one-to-either conversions.</figcaption>
</div>

Experiments demonstrate the effectiveness of our framework and representation on emotion modeling. Additionally, our method enables new capabilities to control the arousal levels of generation under the same lead sheet, leading to more flexiable emotion controls.

# Generation Samples

A selection of generation samples are shown below. Models are denoted as **<representation(stage)>**. For example, REMI(one) denotes the one-stage generation model with REMI representation as the baseline, and REMI(two) denotes the two-stage generation as one variant. The first section (**4Q generations**) shows generated examples for each Quadrant, and the second section (**Same Lead Sheet, Different Arousal**) presents generations of different arousal levels under the same lead sheet.

## 4Q generations

### Q1 (High Valence, High Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI(one) - Baseline</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI(two) - Variant</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional(two) - Ours</td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q1_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q1_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q1_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q2 (Low Valence, High Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI(one) - Baseline</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI(two) - Variant</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional(two) - Ours</td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q2_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q2_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q2_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q3 (Low Valence, Low Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI(one) - Baseline</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI(two) - Variant</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional(two) - Ours</td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q3_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q3_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/Functional(two)/Q3_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q4 (High Valence, Low Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI(one) - Baseline</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI(two) - Variant</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional(two) - Ours</td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

## Same Lead Sheet, Different Arousal

### Positive lead sheet**

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>High Arousal</th>
    <th>Low Arousal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3">REMI(two) - Variant</th>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <th rowspan="3">Functional(two) - Ours</th>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>


### Negative lead sheet**

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>High Arousal</th>
    <th>Low Arousal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3">REMI(two) - Variant</th>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <th rowspan="3">Functional(two) - Ours</th>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>



[jekyll-organization]: https://github.com/jekyll
