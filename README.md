<img alt="spectroghost-logo" src="./assets/images/logo.png" style="margin-left:auto; margin-right:auto; display:block; width:200px;"/>

# SpectroGhost

**SpectroGhost** is a lightweight, browser-based spectrogram creator designed for analyzing and visualizing sound with high precision. It converts audio files into detailed, zoomable spectrograms, helping users reveal hidden sonic structures, embedded messages, and fine-grained frequency patterns — all locally, with no backend or uploads.

[**View Live Demo**](nqrlabs.com/SpectroGhost/)

## Overview

SpectroGhost performs real-time Short-Time Fourier Transform (STFT) analysis in the browser using a custom FFT engine.  
It supports **linear**, **logarithmic**, **mel**, and **bark** frequency scales, and provides full control over FFT size, hop length, dynamic range, and frequency limits.  
Users can zoom, pan, and inspect time–frequency coordinates with a responsive cursor display, then export publication-quality PNGs containing metadata for reproducible analysis.

Every operation runs client-side using Web Audio and Canvas APIs, making SpectroGhost fully private, portable, and offline-ready.

## Features

- **High-resolution STFT rendering:** Choose FFT size, hop size, and dynamic range.  
- **Multiple frequency scales:** Linear, log, mel, and bark scaling for flexible analysis.  
- **Colormap selection:** Switch between grayscale, viridis, plasma, inferno, magma, jet, hot, cool, and parula gradients.  
- **Interactive exploration:** Zoom with Ctrl + scroll, drag to pan, and double-click to reset.  
- **Invertible mode:** Automatically computes pixel-perfect dimensions for reversible audio processing.  
- **Metadata embedding:** Exports PNGs containing analysis parameters in `tEXt` fields for seamless round-tripping with tools like ReSounder.  
- **Offline operation:** No network connection required; runs entirely in the browser.  
- **Precision export:** Generates true-color 8-bit PNGs using a built-in encoder for maximum fidelity.

## Technical Notes

### Processing Framework

- **STFT Analysis:** Uses a Hann window and custom radix-2 FFT implementation for efficient in-browser transforms.  
- **Frequency Scales:** Supports perceptual (mel, bark) and mathematical (log, linear) frequency mappings.  
- **Dynamic Range Compression:** Converts magnitude to decibels with user-defined range and floor.  
- **Colormaps:** Built-in 256-entry RGBA lookup tables for consistent visualization across color modes.  
- **PNG Encoding:** Encodes spectrograms to valid 8-bit RGBA PNGs with metadata and CRC32 validation — implemented entirely in JavaScript.  
- **Interactivity:** Canvas rendering updates dynamically with hardware-accelerated zoom and pan.

### Web API Usage

SpectroGhost relies solely on browser-native APIs:
- **Web Audio API** for decoding and reading PCM data.  
- **Canvas 2D API** for pixel rendering and scaling.  
- **File and Blob APIs** for reading input and exporting PNGs.  
- **Typed Arrays** for FFT buffers and grayscale magnitude storage.  

No external libraries or frameworks are required.

## Intended Users

SpectroGhost is designed for artists, sound designers, researchers, and ARG creators exploring the boundary between audio and image.  
It is equally valuable for educators and analysts who need a transparent, reproducible way to visualize time–frequency data without proprietary software.  

The tool combines scientific precision with creative flexibility — a window into the hidden geometry of sound.

## Usage

1. Open the app in your browser.  
2. Load an **audio file** (WAV, MP3, FLAC, etc.).  
3. Adjust FFT size, dynamic range, and frequency scale.  
4. Choose a colormap and optional invert mode.  
5. Zoom and pan through the spectrogram to inspect detail.  
6. Click **Export PNG** to save your rendered image with embedded metadata.  

All processing occurs locally; no data leaves your system.

## License

MIT License — free for modification and use. Attribution appreciated if used publicly.  

## Credit

Created by **NQR** for sound explorers, data artists, and anyone who listens with their eyes.  
If you use *SpectroGhost* in an ARG, art piece, or research project, I’d love to hear about it.
