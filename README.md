# Audio Noise Reduction


This project provides a simple audio noise reduction tool aimed at removing background noise from recorded audio using short-time spectral processing. It is suitable for preprocessing audio for speech recognition, podcasts, and other applications where cleaner sound is desired.

---

## Features

- Easy-to-use command-line interface for denoising audio files
- Short-time spectral noise suppression (spectral gating)
- Adjustable parameters for noise profile estimation and attenuation
- Preserves speech quality while reducing steady or broadband noise

---

## Method

The core method uses Short-Time Fourier Transform (STFT) to convert audio into the time-frequency domain, estimates a noise profile (either from a noise-only segment or via a running median), and applies spectral gating to attenuate frequency bins dominated by noise. The processed spectrogram is converted back to the time domain using inverse STFT. Optional smoothing and overlap-add ensure minimal artifacts.

Key steps:

1. Read audio and convert to mono if needed.
2. Compute STFT with a chosen window and hop size.
3. Estimate noise magnitude spectrum from a selected segment or frame statistics.
4. Compute a gain mask (spectral gate) based on SNR thresholds and smoothing.
5. Apply mask to the noisy spectrogram and perform inverse STFT.
6. Export the denoised audio.

---

## Potential Improvements / Future Work

- Implement adaptive noise estimation for non-stationary noise
- Add a GUI for interactive parameter tuning and real-time preview
- Integrate machine-learning based denoisers (e.g., DNN or RNNoise) for improved quality
- Support batch processing and different audio formats/bit depths
- Add unit tests and CI for reproducibility

---

## Citation

If you use this project in academic work, please cite or reference this repository.
