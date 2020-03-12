# Voice Conversion Challenge 2020 baseline: CycleVAE w/ PWG vocoder

Official homepage: [http://www.vc-challenge.org/](http://www.vc-challenge.org/)

## Introduction

<p align="justify"> 
This repo provides a cyclic variational autoencoder (CycleVAE)-based voice conversion (VC) system with parallel WaveGAN (PWG)-based vocoder for Voice Conversion Challenge 2020 (VCC2020). VCC2020 contains intra-lingual VC (Task1) and cross-lingual VC (Task2) tasks. Task1 includes four English source and four English target speakers. Task2 includes the same English source speakers but other six non-English (German/Finnish/Mandarin) target speakers. The goal is to convert the speaker identity of source speech to target speakers while keeping the same English contents. 
</p>

## CycleVAE w/ PWG vocoder

<p align="justify"> 
For this baseline VC system, WORLD-based acoustic features, which include spectral (further parameterized into mcep), pitch (f0), and aperiodic (ap) features, are adopted. The CycleVAE model only converts the spectral features. Logarithmic f0 is linearly converted and ap is kept the same as source speaker. 
</p>

<p align="justify"> 
Two training processes of PWG vocoder are provided in this repo. The first PWG vocoder is trained with natural acoustic features and natural waveforms. The second PWG vocoder is trained with artificial and natural acoustic features and natural waveforms. Specifically, the artificial acoustic features include self-reconstructed and pseudo converted (target->source->target) acoustic features, which are generated by the CycleVAE and have the matched temporal structure with the natural waveforms. Because of the reduction of the mismatch between training and testing data, the second PWG vocoder achieves higher speech quality when the input is the converted acoustic features.
</p>  

## Model and demo 

The trained CycleVAE and PWG models can be accessed [here](https://drive.google.com/drive/folders/1OLdzE6rX_UBtlyUh0XDVCbz28xPFcpxz?usp=sharing).  
The generated samples can be accessed [here](https://drive.google.com/drive/folders/1DD7IVLDCPHi7S8flgLvzx-YPCR7GACzV?usp=sharing).


## Corpus

Only VCC2020 corpus is involved in both CycleVAE and PWG trainings.

- **VCC2020** contains all training data of the challenge. Please follow the instruction from the organizers to download it in the desired directory. (default is `baseline/egs/cyclevae/wav_24kHz/`)

## Usage and requirements

Please check `baseline/README.md`.


---
## References

* CycleVAE [[paper]](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2307.pdf) [[github]](https://github.com/patrickltobing/cyclevae-vc)

* PWG [[paper]](https://arxiv.org/abs/1910.11480) [[github]](https://github.com/kan-bayashi/ParallelWaveGAN)


---
## Authors

Development:   
Patrick Lumban Tobing @ Nagoya University ([@patrickltobing](https://github.com/patrickltobing))  
Yi-Chiao Wu @ Nagoya University ([@bigpon](https://github.com/bigpon))  

Advisor:  
Tomoki Toda @ Nagoya University

E-mail:  
`patrick.lumbantobing@g.sp.m.is.nagoya-u.ac.jp`  
`yichiao.wu@g.sp.m.is.nagoya-u.ac.jp`  
`tomoki@icts.nagoya-u.ac.jp`

