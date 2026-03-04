# TS Voltage Reader (Divider + Isolation)

## ISSUE

Almost all ICs in the low-voltage system operate at **low voltage**, but the tractive system (TS) can be as high as **600 V**.

To safely process and compare the TS voltage, we must:

- **Scale** it down to a manageable level (e.g., ~1–2 V)
- Maintain **isolation** between the TS side and the low-voltage side (LVS)

## FIX

- A **resistive voltage divider** to scale 0–600 V down to ~0–1.2 V
- An **isolation amplifier** to represent galvanic isolation (simulation model)

Reference (concept video): <https://www.youtube.com/watch?v=2PVD46IhLro>

## USAGE

### Divider values

- Top resistor: **3 × 470 kΩ** in series (so each sees < 200 V)
- Bottom resistor: **2.8 kΩ**

### Divider calculation

The divider output is:

$$
V_{out} = V_{TS} \cdot \frac{R_{bottom}}{R_{top} + R_{bottom}}
$$

$$
V_{out} = 600\text{ V} \cdot \frac{2.8\text{k}\Omega}{1.41\text{ M}\Omega + 2.8\text{k}\Omega}
\approx 1.189\text{ V}
$$

### Isolation in the simulation

- The divider output is fed into an **isolation amplifier** block to represent isolation between TS and LVS.
- Finally, a **voltage-dependent voltage source (gain = 1)** is used as a convenient way to carry the scaled value forward in the schematic.
