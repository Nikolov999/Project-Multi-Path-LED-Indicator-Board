# Design Summary

## Final topology

### Branch 1

```text
+9V -> R1 625Ω -> D1 -> D2 -> GND
```

Two LEDs are in series.

### Branch 2

```text
                         +-> D3 -> GND
+9V -> R2 780Ω -> node
                         +-> D4 -> GND
```

Two LEDs are in parallel after one resistor.

### Branch 3

```text
                                      +-> D5 -> GND
+9V -> R3 500Ω -> R4 500Ω -> node
                                      +-> D6 -> GND
```

Two resistors are in series before a parallel LED pair.

## Approximate current map

```text
Branch 1: 8.00 mA
Branch 2: 8.97 mA total
Branch 3: 7.00 mA total

Total:    23.97 mA
```

## PCB implementation

- Through-hole construction
- 2-layer KiCad board definition
- 1.6 mm board thickness
- 137 mm × 97 mm current board outline
- No vias in the current routed design
- 6 × 5 mm THT LED footprints
- 4 × THT resistor footprints
- 1 × 2-pin 2.54 mm THT header
