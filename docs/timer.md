# Timer (Flashing Signal)

## ISSUE

Generate a square wave in the **2–5 Hz** range at **~50% duty cycle** to flash the LED.

## FIX

Use an **NE555 timer** in astable mode.

Reference (concept video): <https://www.youtube.com/watch?v=oZzjmAbyyIQ>

## USAGE

Component values:

- $R_a = 1\text{k}\Omega$
- $R_b = 144\text{k}\Omega$
- $C = 1\,\mu\text{F}$

### Why these values?

For a 555 in astable mode, common approximations are:

$$
f \approx \frac{1.44}{(R_a + 2R_b)\,C}
$$

$$
\mathrm{DutyCycle} \approx \frac{R_a + R_b}{R_a + 2R_b}
$$

Substituting the chosen values:

$$
f \approx \frac{1.44}{(1\text{k}\Omega + 2\cdot 144\text{k}\Omega)\cdot 1\,\mu\text{F}}
= \frac{1.44}{289\text{k}\Omega\cdot 1\,\mu\text{F}}
\approx 4.99\text{ Hz}
$$

$$
\mathrm{DutyCycle} \approx \frac{1\text{k}\Omega + 144\text{k}\Omega}{1\text{k}\Omega + 2\cdot 144\text{k}\Omega}
= \frac{145}{289}
\approx 50.17\%
$$

Notes:

- The timer outputs a ~5 Hz square wave with a peak of about **12 V** in this simulation.
- That 12 V logic level is stepped down to **5 V** using a divider before driving the AND gate input.
