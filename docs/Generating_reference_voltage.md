
- ISSUE:
    If the TS voltage is stepped down, then the reference of 60V must also be stepped down.
    This reference must remain a constant DC value.

- FIX:
    Programmable Shunt Regulator (TL431)
    (Working: https://youtu.be/NecbHbGAkkc?t=150&si=9wcEBeXuUM-I3EPt)

- USAGE:
    The TL431 gives a constant DC voltage of 2.5V.
    This has been stepped-down using a voltage divider to achieve 118mV.

    Why 118mV?

        When the TS is at 600V, we know that the isolation amplifier gives 1.189V
        When the TS is at 60V, by the same voltage divider circuit we get 118mV

        Hence 60V at the TS side is referenced by 118mV on the LVS side.

    - Finally a Voltage Dependent Voltage Source with a gain of 1 was used to isolate the ICs from their outputs.
