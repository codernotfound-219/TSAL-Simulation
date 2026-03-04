
The comparator op-amp LT1017 was used for this purpose.
non-inverting input: output from isolation amplifier (reads TS voltage)
inverting input: the output from TL431 (reference to 60V)

The output goes high if the non-inverting input exceeds the inverting input.
A pullup resistor of 10kΩ was used to boost the output.
A zener clamp is used to limit the output to 5V. (for the AND gate)
