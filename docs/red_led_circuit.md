
- ISSUE:
    The LED should glow only when the comparator's output is high and the square wave from timer is high.

- FIX:
    AND gate
    NMOS (switch)

- USAGE
    Inputs to AND gate: comparator output + square wave signal
    the output of the and gate is sent to the gate of NMOS.

    When the AND gate gives a high signal (+5V), the gate is energized and current can now flow from Drain to Source.
    The led is placed at the drain and glows whenever the gate receives +5V
