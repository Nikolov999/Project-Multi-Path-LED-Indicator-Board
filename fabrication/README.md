# Fabrication Outputs

This directory contains the final fabrication outputs exported from KiCad.

## Contents

### `gerbers/`

- Front copper
- Back copper
- Front solder mask
- Back solder mask
- Front silkscreen
- Back silkscreen
- Front paste
- Back paste
- Board outline (`Edge.Cuts`)
- Gerber job file

### `drill/`

- PTH plated-through-hole drill file
- NPTH non-plated-through-hole drill file

### `Project-Multi-Path-LED-Indicator-Board-Gerbers.zip`

A convenience fabrication package containing the Gerber and drill files together.

## Note on paste layers

This board is through-hole based, so the paste layers are not required for manual through-hole assembly. They are retained because they were included in the final KiCad fabrication export and provide a complete record of that export.

## Manufacturing check

Before ordering a PCB, load the Gerber and drill files into KiCad Gerber Viewer or the chosen manufacturer's viewer and verify:

- the board outline is closed;
- copper layers match the intended routing;
- silkscreen is readable;
- solder-mask openings align with pads;
- drill holes align with through-hole pads;
- no unexpected objects appear on fabrication layers.
