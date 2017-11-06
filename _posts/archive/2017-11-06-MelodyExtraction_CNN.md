---
layout: media
title: APPSCI_Journal Paper (submitted)
categories: archive
modified:
excerpt: Classification-Based Singing Melody Extraction Using Deep Convolutional Neural Networks
image:
  feature:
  teaser: /archive/appsci/melodyExtraction.png
  thumb:
---
<hr>
- <b> Classification-Based Singing Melody Extraction Using Deep Convolutional Neural Networks </b><br>
<span style="color:#666666"> <b>Sangeun Kum</b>, Juhan Nam</span><br>
<span style="color:#6aa84f"> Preprints 2017, 2017110027 (doi: 10.20944/preprints201711.0027.v1) </span><br>
|<a href = "https://www.preprints.org/manuscript/201711.0027/v1" target="_blank">PDF</a>|
|<a href = "http://mac-bach.kaist.ac.kr/keums/melodyExtraction/" target="_blank">Demo</a>|
<hr>

<div style="width:600px; border:1px solid black;">
<img src="/images/archive/appsci/melodyExtraction.png"  width="600">
</div>

<h3>Abstract</h3>

<p>Singing melody extraction is the task that identifies the melody pitch contour of singing voice from polyphonic music. Most of the traditional melody extraction algorithms are based on calculating salient pitch candidates or separating the melody source from the mixture. Recently, classification-based approach based on deep learning has drawn much attentions.</p>

<p>In this paper, we present a classification-based singing melody extraction model using deep convolutional neural networks. The proposed model consists of a singing pitch extractor (SPE) and a singing voice activity detector (SVAD). </p>

<li>The SPE is trained to predict a high-resolution pitch label of singing voice from a short segment of spectrogram. This allows the model to predict highly continuous curves. The melody contour is smoothed further by post-processing the output of the melody extractor. 

<li>The SVAD is trained to determine if a long segment of mel-spectrogram contains a singing voice. This often produces voice false alarm errors around the boundary of singing segments. We reduced them by exploiting the output of the SPE. 
<p>
Finally, we evaluate the proposed melody extraction model on several public datasets. The results show that the proposed model is comparable to state-of-the-art algorithms.</p>
  
<h3> Demo </h3> 
|<a href = "http://mac-bach.kaist.ac.kr/keums/melodyExtraction/" target="_blank">Link</a>|

<div style="width:600px; border:1px solid black;">
<img src="/images/archive/appsci/demo_ex1.png"  width="600">
</div>
<li> We target to annotate contemporary Korean pop music, often called "K-pop" </li>
<li> We collected a list of 114 singers from <a href = "https://kpopvocalanalysis.net/" target="_blank">kpopvocalanalysis.net</a>. We obtained five audio files per singer and filtered out songs with duet, chorus singers or rap. As a result, we collected 469 songs.</li>
<li> Using a singing voice detector, we trimmed audio files into 10-sec long segments with voice, thereby obtaining 6787 examples.</li>

