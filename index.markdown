---
layout: home
title: EMO-Disentanger
description: Emotion-driven Piano Music Generation via Two-stage Disentanglement and Functional Representation
github_link: https://github.com/Yuer867/EMO-Disentanger
---

<div align="center">
<video controls width="500">
  <source src="assets/demos/demo_video.mp4" type="video/mp4">
</video>
</div>

Thanks [html-midi-player](https://cifkao.github.io/html-midi-player/) for the MIDI visualization.

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

Experiments demonstrate the effectiveness of our framework and representation on **emotion modeling**. Additionally, our method enables new capabilities to control the arousal levels of generation under the same lead sheet, leading to more flexiable emotion controls.

<div align="center">
  <img src="figures/user_study.png" width=800 alt="">
  <figcaption><strong>Fig.5</strong> Left: The mean opinion score performance on the valence-oriented and arousal-oriented listening tests. For (a-1) and (b-1), the higher score the better performance; for (a-2) and (b-2), the lower score the better performance. Right: The confusion matrices on the 4Q listening tests.</figcaption>
</div>

# Generation Samples

We show some generation samples below from three models:

* **REMI (one)**: one-stage generation model with REMI representation, baseline
* **REMI (two)**: two-stage generation model with REMI representation, one variant of our proposed framework
* **Functional (two)**: two-stage generation model with functional representation, our main proposal

## Same Lead Sheet, Different Arousal Performance

This section presents piano performances with different arousal levels (**Low Arousal**, **High Arousal**) that were generated in the second stage of our framework, based on the same lead sheet (**Lead Sheet**) produced in the first stage. This is a new emotion-based music generation application with our two-stage framework, either with REMI or functional representation.

### Examples with positive valence

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Given Lead Sheet</th>
    <th>High Arousal</th>
    <th>Low Arousal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3">REMI (two)</th>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/positive_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <th rowspan="3">Functional (two)</th>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/positive_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
</table>


### Examples with negative valence

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Given Lead Sheet</th>
    <th>High Arousal</th>
    <th>Low Arousal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="3">REMI (two)</th>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/REMI(two)/negative_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <th rowspan="3">Functional (two)</th>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_0.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_1.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_HA_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/Arousal/functional(two)/negative_LA_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
</table>

## 4Q generations

This section shows generated examples for each Quadrant. It was found that REMI representation has poor performance in valence modeling based on our user study.

### Q1 (High Valence, High Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI (one)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_0_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_1_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q1_2_new.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q1_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q1_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q1_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q1_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q2 (Low Valence, High Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI (one)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_0_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_1_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q2_2_new.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q2_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q2_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q2_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q2_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q3 (Low Valence, Low Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI (one)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_0_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_1_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q3_2_new.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q3_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q3_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q3_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q3_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

### Q4 (High Valence, Low Arousal)

<table class="audio-table">
  <tbody>
    <tr>
      <td>REMI (one)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_0_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_1_new.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(one)/Q4_2_new.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>REMI (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/REMI(two)/Q4_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Functional (two)</td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="assets/demos/4Q/functional(two)/Q4_2.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

## Authors and Affiliations

* Jingyue Huang \
PhD student @ UC San Diego \
jih150@ucsd.edu

* [Ke Chen](https://www.knutchen.com/) \
PhD student @ UC San Diego \
knutchen@ucsd.edu
 
* [Yi-Hsuan Yang](https://affige.github.io/)   
Professor @ National Taiwan University / Joint-Appointed Researcher @ Academia Sinica  
yhyangtw@ntu.edu.tw, affige@gmail.com

[jekyll-organization]: https://github.com/jekyll
