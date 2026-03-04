# TSAL SIMULATION
## TSAL : Red Light System

- OBJECTIVE:
    - A red led should flash ( 2~5 Hz at 50% Duty Cycle) when:
        1. LVS is active
        2. Voltage across DC-Link Capacitor exceeds Threshold


- ASSUMPTIONS:
    1. LVS is assumed to be always active and supplying +12V.
    2. Instead of the DC-Link Capacitor, the Tractive System's voltage is taken for simplicity.
    3. The tractive system's voltage is allowed to go from 0 to 600V in 2 seconds. (RAMP fn.)
    4. The threshold voltage is set to 60V.


- REALIZATION:
    1. Read TS voltage to an appropriate step down value.
    2. Generate a reference voltage that mimicks the threshold value.
    3. Compare the read TS_Voltage and this reference voltage and provide an output high if value exceeds threshold.
    4. Use a timer to generate a 5Hz, 50% duty cycle square wave.
    5. Supply the square wave and the comparator output to an AND gate.
    6. Use the output of the AND gate to trigger a switch turning ON the LED.
    

- DOCUMENTATION:
    - Refer to the following documents to understand how each step of realization was achieved.
        1. docs/TS_Voltage_Reader.md
        2. docs/Generating_reference_voltage.md
        3. docs/comparator.md
        4. docs/timer.md
        5. docs/red_led_circuit.md

    - Proof of Simulation:
        1. docs/simulation_verification.pdf

    - To run the simulation yourself, check out:
        1. docs/running_simulation.md
