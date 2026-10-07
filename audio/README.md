# Audio Test

This folder contains the audio files used to test the amplifier with a real-world input signal.

The goal of this test was to verify the performance of the amplifier using an actual audio waveform instead of only a sinusoidal input.

## Files

### `audio.wav`

Original input audio signal used as the amplifier input.

### `output.wav`

Amplified output signal obtained after passing the audio signal through the circuit.

## Audio Preparation

The original audio was recorded using a mobile device and converted to WAV format.

Python was then used to process and normalize the signal before using it in the LTspice simulation.

Audio characteristics:

- Format: WAV
- Mono audio
- Sample rate: 48 kHz
- Amplitude normalized before simulation

## Evaluation

The input and output waveforms were compared to evaluate:

- Signal amplification
- Waveform preservation
- Output swing
- Clipping behavior

The simulated amplified output remained within the designed output range without severe clipping.
