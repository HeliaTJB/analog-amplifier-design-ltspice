
# Analog Power Amplifier Design
### Multi-Stage BJT Amplifier with Global Negative Feedback

## Overview

This project presents the design and simulation of a multi-stage analog power amplifier developed for an Electronics II course project.

The main objective was to design a complete amplifier capable of driving a **50 Ω load** while satisfying constraints on gain, output swing, efficiency, harmonic distortion, power consumption, input/output resistance, and power-supply rejection.

The final design was implemented and evaluated in **LTspice** and includes:

- Differential input stage
- Current-mirror biasing
- Voltage amplification stages
- Complementary push-pull output stage
- Global negative feedback
- 50 Ω output load

The design was evaluated through DC, AC, transient, distortion, power, impedance, and real-audio simulations.

---

## Project Structure

```text
Analog-Power-Amplifier/
│
├── circuit/
│   ├── README.md
│   └── LTspice schematic files
│
├── audio/
│   ├── README.md
│   ├── audio.wav
│   └── output.wav
│
├── report/
│   ├── README.md
│   └── Electronics_II_Project_Report.pdf
│
└── README.md
```

---

## Circuit Architecture

The amplifier is composed of several transistor-level stages.

### Differential Input Stage

A BJT differential pair is used as the input stage, providing differential amplification and enabling the application of global negative feedback.

### Biasing

Current mirrors are used to establish stable bias currents across the amplifier stages.

A separate current-mirror network is used for the output stage to provide the required bias current independently from the earlier stages.

### Voltage Amplification

Intermediate transistor stages provide the required open-loop voltage gain before the signal reaches the output power stage.

### Output Stage

The output stage uses a complementary **push-pull topology** with NPN and PNP transistors.

This topology was selected to provide:

- High output-current capability
- Improved efficiency
- Symmetric output swing
- Suitable operation with a low-resistance 50 Ω load

Diode-connected transistors are used to reduce crossover distortion.

---

## Global Negative Feedback

Global negative feedback is applied from the final output node to the inverting input of the differential stage.

The feedback network uses:

```text
Rf = 190 kΩ
Rg = 10 kΩ
```

The ideal closed-loop gain is therefore:

```text
Av ≈ 1 + Rf/Rg ≈ 20
```

The simulated closed-loop gain at 1 kHz was:

```text
Av = 19.88
```

Negative feedback significantly improved linearity, reduced distortion, and prevented early clipping compared with the open-loop configuration.

---

## DC Operating Point

The final circuit was analyzed using LTspice operating-point simulations.

Important bias results include:

- Output DC voltage close to 0 V
- Output-stage bias current ≈ 2.1 mA
- Stable biasing across the amplifier stages

The biasing network was designed to provide sufficient current for the required output swing without excessive power consumption.

---

## Output Swing and Efficiency

The amplifier was designed to generate a large sinusoidal output swing across a 50 Ω load.

The final design achieved:

```text
Maximum demonstrated output swing ≈ 17.4 Vpp
```

The output stage efficiency was approximately:

```text
η ≈ 72%
```

This satisfies the project requirement of more than 60% efficiency.

---

## Harmonic Distortion

Total Harmonic Distortion (THD) was evaluated using a 1 kHz sinusoidal input.

### Normal Operation

```text
THD ≈ 0.0287%
```

### With Bias-Source Noise

Noise sources were introduced in series with the resistors controlling the current-mirror bias currents.

The resulting distortion was:

```text
THD ≈ 0.0416%
```

The increase in distortion remains small, showing that the amplifier maintains good linearity under bias perturbations.

---

## Power-Supply Rejection

Power-supply rejection was evaluated by applying a sawtooth ripple to the positive and negative supply rails.

The measured result was approximately:

```text
PSRR ≈ 120.45 dB
```

This indicates strong rejection of supply-voltage variations at the output.

---

## Input and Output Resistance

The differential input resistance was measured using a small-signal AC test source:

```text
Rin,diff ≈ 16.7 MΩ
```

The output resistance was measured after removing the 50 Ω load and applying a test source at the output:

```text
Rout ≈ 0.473 Ω
```

The low output resistance allows the amplifier to drive low-impedance loads effectively.

---

## Power Consumption

For a 1 kHz sinusoidal input with amplitude 50 mV, the total circuit power consumption was:

```text
Ptotal ≈ 140.6 mW
```

This satisfies the project requirement of:

```text
Ptotal ≤ 190 mW
```

---

## Real Audio Test

The amplifier was also evaluated using a real recorded audio signal rather than only sinusoidal test signals.

The original recording was converted to WAV format and processed using Python before being applied to the LTspice circuit.

Audio preprocessing included:

- Mono audio
- 48 kHz sample rate
- Amplitude normalization

The amplified waveform preserved the input signal shape without severe clipping.

The corresponding files are available in:

```text
audio/
├── audio.wav
└── output.wav
```

---

## Final Results

| Parameter | Result |
|---|---:|
| Closed-loop gain @ 1 kHz | 19.88 |
| Maximum output swing | 17.4 Vpp |
| Output-stage efficiency | 72% |
| Total power consumption | 140.6 mW |
| THD | 0.0287% |
| THD with bias noise | 0.0416% |
| PSRR | 120.45 dB |
| Differential input resistance | 16.7 MΩ |
| Output resistance | 0.473 Ω |
| Output load | 50 Ω |
| Circuit cost | 145 |

---

## Tools

- LTspice
- Python
- WAV audio processing

---

## Key Takeaway

The project demonstrates how transistor-level analog design, biasing, complementary output stages, and global negative feedback can be combined to build a power-efficient and low-distortion amplifier capable of driving a low-resistance load.

A major design challenge was achieving a large output swing while maintaining low power consumption, low distortion, and stable biasing.

---

## Report

A complete description of the theoretical calculations, design decisions, LTspice simulations, and performance evaluation is available in:

```text
report/Electronics_II_Project_Report.pdf
```

---

## Author

**Helia Tajabadi**  
Electrical Engineering  
Sharif University of Technology
