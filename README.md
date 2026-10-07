
# Analog Power Amplifier Design and Simulation

A complete analog power amplifier designed and simulated in **LTspice** as an Electronics II course project.

The amplifier combines a differential input stage, current-mirror biasing, voltage amplification stages, a complementary push-pull power stage, and global negative feedback. The design was evaluated for gain, distortion, efficiency, power consumption, PSRR, input/output resistance, and real-audio amplification.

## Project Highlights

- Designed a complete multi-stage analog amplifier from transistor-level building blocks
- Implemented a complementary push-pull output stage for driving a 50 Ω load
- Designed a global negative-feedback network for stable closed-loop gain
- Performed DC, AC, transient, THD, PSRR, and impedance analyses in LTspice
- Evaluated power consumption and output-stage efficiency
- Tested the final amplifier using a real audio signal
- Used Python for audio preprocessing and normalization

## Circuit Architecture

The final amplifier consists of:

- Differential input stage
- Current-mirror bias networks
- Voltage amplification stages
- Complementary push-pull output stage
- Global negative feedback
- 50 Ω output load

The output-stage biasing was implemented using a separate current mirror, while diode-connected transistors were used to reduce crossover distortion.

## Global Negative Feedback

The final output voltage is sampled and fed back to the inverting input of the differential stage.

The feedback network uses:

- `Rf = 190 kΩ`
- `Rg = 10 kΩ`

giving an ideal closed-loop gain of approximately:

```text
Av ≈ 1 + Rf/Rg ≈ 20
```

The simulated closed-loop gain at 1 kHz was:

```text
Av = 19.88
```

## Performance

| Parameter | Result |
|---|---:|
| Closed-loop gain @ 1 kHz | 19.88 |
| Maximum demonstrated output swing | 17.4 Vpp |
| Output-stage efficiency | 72% |
| Total power consumption @ 50 mV, 1 kHz | 140.6 mW |
| THD | 0.0287% |
| THD with bias-source noise | 0.0416% |
| PSRR | 120.45 dB |
| Differential input resistance | 16.7 MΩ |
| Output resistance | 0.473 Ω |
| Output load | 50 Ω |
| Circuit cost | 145 |

## Simulation and Verification

The final design was evaluated using several analyses in LTspice:

- DC operating-point analysis
- AC frequency analysis
- Closed-loop gain measurement
- Transient analysis
- Output swing and clipping analysis
- Power consumption measurement
- Output-stage efficiency measurement
- Total harmonic distortion (THD)
- THD under noisy bias conditions
- Power-supply rejection ratio (PSRR)
- Differential input resistance measurement
- Output resistance measurement

## Real Audio Test

In addition to sinusoidal test signals, the amplifier was evaluated using a real recorded audio waveform.

The audio signal was converted to WAV format and processed using Python before being applied to the LTspice model.

Audio preprocessing included:

- Mono conversion
- 48 kHz sampling rate
- Amplitude normalization

The resulting output waveform was amplified without severe clipping.

## Repository Structure

```text
.
├── README.md
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
└── report/
    ├── README.md
    └── Electronics_II_Project_Report.pdf
```

## Tools and Skills

**Tools**

- LTspice
- Python

**Topics**

- Analog circuit design
- BJT amplifier design
- Differential amplifiers
- Current mirrors
- Push-pull power amplifiers
- Negative feedback
- Biasing
- Harmonic distortion analysis
- Power and efficiency analysis
- PSRR
- Small-signal impedance analysis
- Audio signal processing

## Documentation

The complete design process, theoretical calculations, simulation methodology, and detailed results are available in the [`report/`](report/) directory.

The LTspice circuit files are available in [`circuit/`](circuit/), and the real-audio test files are available in [`audio/`](audio/).

## Author

**Helia Tajabadi**
