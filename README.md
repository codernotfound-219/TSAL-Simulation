# TSAL Simulation

This repository contains an LTspice simulation of a TSAL-style **red warning light system**.

In this context, **TSAL** refers to a *Tractive System Active Light*: a red LED that flashes when the (simulated) tractive-system voltage exceeds a defined threshold.

## Objective

A red LED should flash (**2–5 Hz**, **50% duty cycle**) when:

1. The **LVS** (low-voltage supply) is active
2. The voltage across the **DC-Link capacitor** (approximated here by the tractive system voltage) exceeds a threshold

## Assumptions

1. The LVS is assumed to always be active and supply **+12 V**.
2. Instead of modeling the DC-Link capacitor directly, the tractive system (TS) voltage is used for simplicity.
3. The TS voltage ramps from **0 V to 600 V** in **2 seconds** (using an LTspice `RAMP()` style behavior).
4. The threshold voltage is set to **60 V**.

## Realization (Implementation)

1. Read the TS voltage and **step it down** to a low-voltage signal.
2. Generate a **reference voltage** that represents the *same threshold* on the low-voltage side.
3. Compare the stepped-down TS voltage against the reference; output logic-high when TS > threshold.
4. Use a timer to generate a **~5 Hz**, **50% duty** square wave.
5. AND the square wave with the comparator output.
6. Use the AND output to drive a switch that turns the LED on/off.

## Documentation

Each stage of the design is explained in the following documents:

1. [docs/TS_Voltage_Reader.md](docs/TS_Voltage_Reader.md)
2. [docs/Generating_reference_voltage.md](docs/Generating_reference_voltage.md)
3. [docs/comparator.md](docs/comparator.md)
4. [docs/timer.md](docs/timer.md)
5. [docs/red_led_circuit.md](docs/red_led_circuit.md)

### Proof of simulation

- [docs/simulation_verification.pdf](docs/simulation_verification.pdf)

### Run the simulation

- See [docs/running_simulation.md](docs/running_simulation.md)
- Falstad Simulation: `download the falstad-sample-tsal.txt and run it in falstad.com`
