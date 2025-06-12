# -Voice-Separation-from-Music-Using-Time-Domain-Segmentation
# Voice Separation from Music Using Time-Domain Segmentation

MATLAB-based system to isolate individual vocal tracks from a mixed audio file (e.g., song duets) via manual time-domain segmentation.

## Features
- Extracts vocal segments with **85% purity** (Levine) and **80% purity** (SZA).
- Simple, dependency-free MATLAB implementation.
- Demonstrates core DSP concepts for educational use.

## Usage
1. Place your audio file in `audio_samples/input/`.
2. Update time segments in `separate_voices.m` (lines 8–11).
3. Run the script to generate separated vocals in `audio_samples/output/`.

## Code Example
```matlab
% Load audio file
[input_audio, fs] = audioread('audio_samples/input/What_Lovers_Do_ft_SZA.mp3');

% Define time segments (in seconds)
levine_segment = [0, 61];  % Levine's vocals
sza_segment = [62, 76];    % SZA's vocals

% Extract and save segments
audiowrite('audio_samples/output/levine_voice.wav', input_audio(round(levine_segment(1)*fs : round(levine_segment(2)*fs), fs);
audiowrite('audio_samples/output/sza_voice.wav', input_audio(round(sza_segment(1)*fs : round(sza_segment(2)*fs), fs);
