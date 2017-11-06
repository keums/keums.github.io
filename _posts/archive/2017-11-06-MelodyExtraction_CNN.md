---
layout: media
title: APPSCI_Journal Paper(submitted)
categories: archive
modified:
excerpt: Classification-Based Singing Melody Extraction Using Deep Convolutional Neural Networks
image:
  feature:
  teaser: archive/appsci/melodyExtraction.png
  thumb:
---
<hr>
- <b> Classification-Based Singing Melody Extraction Using Deep Convolutional Neural Networks </b><br>
<span style="color:#666666"> <b>Sangeun Kum</b>, Juhan Nam</span><br>
<span style="color:#6aa84f"> Preprints 2017, 2017110027 (doi: 10.20944/preprints201711.0027.v1) </span><br>
|<a href = "https://www.preprints.org/manuscript/201711.0027/v1" target="_blank">PDF</a>|
|<a href = "http://mac-bach.kaist.ac.kr/keums/melodyExtraction/" target="_blank">Demo</a>|
<hr>

<div style="width:500px; border:1px solid black;">
<img src="/images/archive/archive/appsci/melodyExtraction.png"  width="500"  >
</div>

<p>
  The definition of "Melody extraction" is that automatically obtaining the f0 curve of the predominant melodic line drawn from multiple sources. Various algorithms have been proposed so far and they can be broadly classified into three categories:<br>
<p>
  <ul>
  <li> A salience-based approaches use a salience function to estimate the salience of each possible pitch value.</li>
  <li> A source-separation based approaches isolate the melody source from the mixture. These two approaches are majority of the melody extraction algorithms</li>
  <li>On the other hand, Data-driven based approach is rarely attempted.</li>
  </ul>
</p>

<p>
Therefore, we addressed some issues. No one attempt to use deep neural network to extract melody.
Deep learning is really hot keyword in research area in these days. Deep learning has proved having great performance with sufficient labeled data and computing power. So we tried to use deep learning to estimate the melody contours.
</p>

<br>
<div style="width:600px; border:1px solid black;">
  <img src="/images/archive/ISMIR2016/MCDNN.png"  width="600"  >
</div>

<p>We used multi-column deep neural network (MCDNN).
<ul>
  <li>
    The MCDNN was originally devised as an ensemble method to improve the performance of DNN for image classification. Several deep neural columns become experts on inputs in different ways, therefore by averaging each predictions, we can decrease the errors.</li>
  <li>
    It was applied to image denoising as well. In this approach, each column was trained on a different type of noise and the outputs were weighted to handle noise types.</li></ul>
Our proposed model may pose half-way between these two approaches.</p>

<br>
<div style="width:600px; border:1px solid black;">
<img src="/images/archive/ISMIR2016/melody_extraction.png"  width="500"  >
</div>

<p>
This is our architecture of a proposed methods.
<ul>
<li> By using Multi Column DNN, our model produces a finer pitch resolution more accurately. Each of the DNN columns takes multi-fame spectrogram frames as input to capture contextual information from neighboring frames. </li>
<li> And each DNN columns predict pitch labels with different resolutions. The lowest resolution is 1 semitone. The next one has higher resolutions by two times. Pitch predictions with lower resolutions are actually expanded by replicating each element so that the output sizes are the same for the all columns. </li>
<li>
Given the outputs of the columns, we compute the combined posterior likelihood. Mathematically, we multiplied all probabilities together, which corresponds to summing the log-likelihood of the predictions.

<br><br>
<p align="center"><img src="/images/archive/ISMIR2016/sum.png"  width="400" ></p> <br>
</li>
</ul>
</p>
<p>
Here we verify it by illustrating three examples from different models.
We selected an opera song from the ADC2004 dataset, because this song has dynamic pitch motions such as high pitch and strong vibrato.</p>

<div style="width:33%; float:left;">
<img src="/images/archive/ISMIR2016/result_1.png"  width="300"  >
</div>
<div style="width:33%; float:left;">
<img src="/images/archive/ISMIR2016/result_2.png"  width="300"  >
</div>
<div style="width:33%; float:left;">
<img src="/images/archive/ISMIR2016/result_3.png"  width="300"  >
</div>
<div style="clear:both"></div>



<ul>
<li>A left one is from the Single Column DNN with a pitch resolution of 4 and trained only with the RWC dataset.</li>
<li>A middle one is from the same SCDNN but trained with additional data. Comparing the first models, the additional songs help tracking the vibrato.But the second model still misses the whole excursion.</li>
<li>A right one is from the 1-2-4 Multi-column DNN. With the additional resolutions, the Multi-column DNN makes further improvement, tracking the pitch contours quite precisely.</li>


<p>
</p>

<p>
</p>
