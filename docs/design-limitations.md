# Design Limitation — Parallel LEDs Sharing One Resistor

Branches 2 and 3 intentionally contain parallel LEDs that share upstream current-limiting resistance.

For the learning calculations, the LEDs are treated as identical:

- D3 and D4 are assumed to split Branch 2 current equally.
- D5 and D6 are assumed to split Branch 3 current equally.
- Each LED is approximated as having a forward voltage of 2 V.

This is an **idealized educational assumption**, not a guarantee for real hardware.

Real LEDs have manufacturing tolerances. Two nominally identical LEDs can have slightly different forward voltages. When connected directly in parallel, the LED with the lower forward voltage can take more current than the other LED. The current may therefore **not split evenly** in practice.

For a more robust real-world design, each parallel LED would normally receive its own current-limiting resistor, or the LEDs would be controlled by an appropriate constant-current circuit.

The shared-resistor arrangement is retained here deliberately because this project is a learning exercise in:

- voltage behavior in parallel branches;
- current splitting at junctions;
- series versus parallel analysis;
- total branch current versus individual LED current.

It should not be interpreted as a recommended production topology for independently controlled LEDs.
