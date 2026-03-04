# Generating the Reference Voltage (Threshold)

## ISSUE

Once the TS voltage is stepped down to a low-voltage signal, the **threshold (60 V)** must be represented on the same scaled basis.

That scaled threshold must be:

- A **constant DC** value
- Compatible with **low-voltage IC inputs**

## FIX

Use a **programmable shunt regulator (TL431)** as a stable reference source, then scale it using a divider.

Reference (concept video): <https://youtu.be/NecbHbGAkkc?t=150>

## USAGE

### What value do we need?

From the TS voltage reader stage:

- At $V_{TS}=600\text{ V}$, the scaled output is $1.189\text{ V}$.

Because the divider is linear, the scaled value at $60\text{ V}$ is simply one-tenth:

$$
V_{scaled}(60\text{ V}) = 1.189\text{ V} \cdot \frac{60}{600} \approx 0.1189\text{ V} \approx 118\text{ mV}
$$

So, **60 V on the TS side** corresponds to **~118 mV** on the low-voltage side.

### Creating ~118 mV from the TL431

The TL431 provides a stable reference around **2.5 V**. A divider is then used to produce the required level:

$$
V_{ref} = 2.5\text{ V} \cdot \frac{R_2}{R_1 + R_2}
$$

To target $V_{ref}\approx 0.118\text{ V}$, the divider ratio needs to be:

$$
\frac{R_2}{R_1 + R_2} \approx \frac{0.118}{2.5} \approx 0.0472
$$

In other words, choose $R_1$ roughly **20×** $R_2$ (many resistor pairs will work; exact values depend on your preferred current draw).

### Buffering / isolation inside the schematic

As with the other stages, a **voltage-dependent voltage source (gain = 1)** can be used as a clean way to pass the reference forward without loading effects.
