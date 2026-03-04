# Red LED Driver (Gating + Switch)

## ISSUE

The LED should glow **only when both conditions are true**:

1. Comparator output is high (TS voltage above threshold)
2. Timer output is high (flash waveform)

## FIX

- An **AND gate** to combine both logic conditions
- An **NMOS** used as a switch to drive the LED

## USAGE

- Inputs to AND gate: **comparator output** and **timer square wave**
- AND gate output drives the **gate** of the NMOS

When the AND output is high (~+5 V):

- The NMOS turns on, allowing current to flow from **drain to source** (low-side switch behavior)
- The LED turns on during the “high” portion of the timer waveform, but only if the comparator condition is also true
