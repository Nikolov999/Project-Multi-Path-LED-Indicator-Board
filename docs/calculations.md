# Electrical Calculations

## Given design targets

- Supply voltage: **E = 9 V**
- Approximate LED forward voltage: **Vf ≈ 2 V per LED**
- Desired total board current: **It ≈ 24 mA**

The final design uses three major parallel branches.

---

## Branch 1 — two LEDs in series

Topology:

```text
+9V -> R1 -> D1 -> D2 -> GND
```

The LED forward-voltage drops add because D1 and D2 are in series:

```text
Vf,total = 2 V + 2 V = 4 V
```

Voltage across R1:

```text
Vr1 = 9 V - 4 V = 5 V
```

Chosen branch current:

```text
I1 = 8 mA = 0.008 A
```

Required resistance:

```text
R1 = Vr1 / I1
R1 = 5 / 0.008
R1 = 625 ohm
```

Resistor power:

```text
Pr1 = Vr1 * I1
Pr1 = 5 * 0.008
Pr1 = 0.040 W
```

Because D1 and D2 are in series:

```text
I(D1) = I(D2) = 8 mA
```

---

## Branch 2 — one resistor feeding two parallel LEDs

Topology:

```text
                 +-> D3 -> GND
+9V -> R2 -> node
                 +-> D4 -> GND
```

D3 and D4 are in parallel, so each LED is across the same node-to-ground voltage.
Under the simplified design assumption:

```text
Vnode ≈ Vf ≈ 2 V
```

Voltage across R2:

```text
Vr2 = 9 V - 2 V = 7 V
```

Chosen resistor:

```text
R2 = 780 ohm
```

Actual total branch current:

```text
I2 = Vr2 / R2
I2 = 7 / 780
I2 ≈ 0.008974 A
I2 ≈ 8.97 mA
```

Under the idealized assumption that D3 and D4 are identical and share current equally:

```text
I(D3) ≈ 4.49 mA
I(D4) ≈ 4.49 mA
```

Resistor power:

```text
Pr2 = 7 * 0.008974
Pr2 ≈ 0.0628 W
```

---

## Branch 3 — two series resistors feeding two parallel LEDs

Topology:

```text
                             +-> D5 -> GND
+9V -> R3 -> R4 -> node
                             +-> D6 -> GND
```

D5 and D6 are parallel, so the common node is approximated as:

```text
Vnode ≈ 2 V
```

The two series resistors therefore drop:

```text
Vr,total = 9 V - 2 V = 7 V
```

Series resistance:

```text
Rtotal = R3 + R4
Rtotal = 500 + 500
Rtotal = 1000 ohm
```

Branch current:

```text
I3 = 7 / 1000
I3 = 0.007 A
I3 = 7 mA
```

Because R3 and R4 are equal and carry the same series current, each drops:

```text
Vr3 = 3.5 V
Vr4 = 3.5 V
```

Power in each resistor:

```text
Pr3 = 3.5 * 0.007 = 0.0245 W
Pr4 = 3.5 * 0.007 = 0.0245 W
```

Under the idealized equal-current-sharing assumption:

```text
I(D5) ≈ 3.5 mA
I(D6) ≈ 3.5 mA
```

---

## Total board current

```text
It = I1 + I2 + I3
It = 8 mA + 8.97 mA + 7 mA
It ≈ 23.97 mA
```

This is effectively the original target of approximately **24 mA**.

Approximate source power:

```text
Psource = E * It
Psource = 9 * 0.02397
Psource ≈ 0.216 W
```

---

## Key formulas used

```text
Series LED voltage:
Vf,total = Vf1 + Vf2 + ...

Voltage left for resistor:
Vr = E - Vf,total

Ohm's law:
I = V / R
R = V / I

Series resistors:
Rtotal = R1 + R2 + ...

Current at a junction:
Iin = Iout1 + Iout2 + ...

Resistor power:
P = V * I
```
