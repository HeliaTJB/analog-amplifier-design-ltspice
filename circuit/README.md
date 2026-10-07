# Circuit

This folder contains the LTspice circuit files for the final Electronics II project.

The designed amplifier includes:

- Differential input stage
- Current-mirror biasing
- Voltage amplification stages
- Complementary push-pull output stage
- Global negative feedback
- 50 Ω output load

## Feedback Network

The global negative feedback network is connected from the final output node to the inverting input of the differential stage.

Feedback resistor values:

- Rf = 190 kΩ
- Rg = 10 kΩ

The resulting closed-loop gain is approximately 20.

The simulated closed-loop voltage gain at 1 kHz is:

- Av ≈ 19.88

## Output Stage

The output stage uses a complementary push-pull topology with NPN and PNP transistors.

A separate current-mirror bias network is used for the output stage, with a bias current of approximately 2 mA.

Diode-connected transistors are used to reduce crossover distortion.

## Simulations

The LTspice circuit was evaluated using:

- DC operating-point analysis
- AC analysis
- Transient analysis
- Output swing and clipping analysis
- Power measurements
- THD analysis
- PSRR analysis
- Input resistance measurement
- Output resistance measurement

Open the `.asc` file using LTspice to view and simulate the final circuit.
