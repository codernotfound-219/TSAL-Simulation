
- ISSUE: 
    Almost all ICs operate on Low Voltage. The tractive system is expected to be at 600V. In order to compare we must step this voltage down to manageable levels.

- FIX:
    Isolation Amplifier
    (Find its working here: https://www.youtube.com/watch?v=2PVD46IhLro)

- USAGE:
    - The 600V is stepped down using a voltage divider circuit.
    - Top resistor (3x 470kΩ in series) {to drop the voltage across each to < 200V}
    - Bottom resistor (2.8kΩ)

    Voltage division:
        600 * 2.8k / (3*470k + 2.8k) = 1.189 V

    - Isolation between the TS and LVS is achieved by supplying this voltage as the input to the ISOLATION AMPLIFIER.

    - Finally, a voltage dependent voltage source with a gain of 1 is used to represent the TS voltage value.
