# 🎙️ Speech Enhancement using Spectral Subtraction (MATLAB)

## Overview

This project implements a **speech enhancement algorithm** using the spectral subtraction technique to reduce background noise from corrupted speech signals.

The system operates in the **frequency domain**, estimating noise characteristics and subtracting them from the noisy speech spectrum to reconstruct a cleaner signal.

The implementation demonstrates fundamental concepts of **Digital Signal Processing (DSP)** including FFT-based analysis, frame processing, and signal reconstruction.

---

## 🎯 Objective

To improve speech intelligibility by reducing additive noise present in recorded speech signals.

---

## 🧠 Methodology

The enhancement process follows these steps:

1. Load noisy speech signal.

2. Divide signal into overlapping frames.

3. Apply Hamming windowing.

4. Perform FFT to convert into frequency domain.

5. Estimate noise spectrum from initial frames.

6. Apply spectral subtraction:

   |X(k)| = max(|Y(k)| − αD(k), 0)

7. Reconstruct enhanced signal using inverse FFT.

8. Normalize and save enhanced audio output.

The algorithm workflow and theory are described in the project report .

---

## 🛠️ Tools Used

* MATLAB
* Signal Processing Toolbox
* FFT / IFFT based analysis

---

## 📊 Results

* Background noise reduced in corrupted speech signals
* Improved waveform clarity after enhancement
* Output verified through waveform comparison and listening tests

Example comparison:

* Noisy Speech Signal
* Enhanced Speech Signal

(See results folder for outputs.)

---

## 📁 Repository Structure

```id="p1mk4u"
speech-enhancement-spectral-subtraction/
│
├── code/
│   └── spectral_subtraction.m
│
├── results/
│   └── waveform_comparison.png
│ 
├── docs/
│   └── project_report.pdf
│
├── README.md
└── LICENSE
```

---

## 👨‍💻 My Contributions

* Implemented spectral subtraction algorithm in MATLAB
* Performed frequency-domain noise estimation
* Generated enhanced speech reconstruction
* Analyzed waveform improvements

---

## 🎓 Academic Context

Developed as a Digital Signal Processing mini project demonstrating practical implementation of speech enhancement techniques.

---

## 👥 Team

Harisankar H
Hashim S N
Joshua Felix
Kesav S P
Livin R L
Pranav J P
Sreekanth S K
Vibhu V

---

## 📄 License

MIT License — for academic and learning purposes.
