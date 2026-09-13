# Plastic-BuildUp-on-Brain

A Computer Model of Microplastic Damage to Neurons: How Plastic Build-Up May Slow Down Brain Signals

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/10fjNTP5aZiLUdd4KUP8QHqCYDtD_INCe)

## Overview

Microplastics are tiny pieces of plastic found almost everywhere, including inside the human body. Scientists do not yet know whether these particles harm the brain. This project uses a computer simulation to test whether plastic build-up inside a neuron's outer layer could slow down or weaken the electrical signals brain cells use to communicate.

## Research Question

Can simulated microplastic accumulation inside a neuron's membrane slow down or weaken its action potentials?

## Method

The Hodgkin-Huxley model of action potential generation was adapted to include a variable for plastic build-up. Membrane capacitance (`C_m`) was scaled across four scenarios:

| Scenario | Membrane Capacitance (µF/cm²) |
|---|---|
| Control | 1.0 |
| Mild | 1.5 |
| Moderate | 2.0 |
| Severe | 2.5 |

Each simulation ran for 60 ms with a 10 µA/cm² stimulus applied between 10 ms and 50 ms.

## Results

<img width="593" height="357" alt="image" src="https://github.com/user-attachments/assets/57c7344c-e229-4857-a40b-d5ea537de70a" />

*Figure 1: Impact of microplastic membrane accumulation on neural firing. Voltage traces for four plastic load factors over a 60 ms simulation.*

| Plastic Load | First Spike (ms) | Peak Voltage (mV) | Spike Count |
|---|---|---|---|
| 1.0 (Control) | 12.11 | 40.73 | 3 |
| 1.5 | 12.81 | 38.73 | 3 |
| 2.0 | 13.50 | 36.49 | 3 |
| 2.5 (Severe) | 14.19 | 34.06 | 3 |

## Key Finding

As plastic load increased from 1.0x to 2.5x:

- First spike latency was delayed by **17.18%** (12.11 ms → 14.19 ms)
- Peak voltage dropped by **6.67 mV** (40.73 mV → 34.06 mV), a **16.38%** reduction
- Spike count remained constant at 3

These results suggest that microplastic build-up could gradually slow down and weaken brain signals, which may contribute to memory and thinking problems over time.

## Files

- `neuron_simulation.ipynb` — the Colab notebook containing all simulation code
- `figure1.png` — voltage traces for all four scenarios
- `LICENSE` — project license

## Tools

Python 3, NumPy, Matplotlib. Runs in Google Colab.

## Limitations

- Membrane capacitance is used as a mathematical proxy for plastic build-up, not a direct measurement
- The model does not include biological responses such as myelin repair or glial activity
- Hodgkin-Huxley constants were originally measured in squid giant axons
- Only a single patch of membrane is modelled, not a full neuron

## References

[1] Hodgkin, A. L. and Huxley, A. F. "A quantitative description of membrane current and its application to conduction and excitation in nerve." *The Journal of Physiology* 117 (1952): 500–544.

[2] Fleury, J. B. and Baulin, V. A. "Microplastics destabilize lipid membranes by mechanical stretching." *Proceedings of the National Academy of Sciences* 118, no. 31 (2021): e2104610118.

[3] Dayan, P. and Abbott, L. F. *Theoretical Neuroscience: Computational and Mathematical Modeling of Neural Systems*. Cambridge: MIT Press, 2001.

