
- ISSUE:
    Generate a 2-5Hz square wave at 50% duty cycle.

- FIX:
    NE555 Timer
    (Working: https://www.youtube.com/watch?v=oZzjmAbyyIQ)

- USAGE:
    Ra = 1kΩ
    Rb = 144kΩ
    Timing Capacitor = 1µF

    Why?
        f = 1.44 / ((Ra + 2Rb) * C) = 4.99 Hz
        Duty Cycle = (Ra + Rb) / (Ra + 2Rb) = 50.17%

    - The timer gives out a square wave of 4.99 Hz at 50.17% Duty cycle, with a peak of 12V.
    - This 12V is stepped down to 5V using a divider. (for AND gate)
