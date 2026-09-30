# Design status and review notes

This repository presents an **unfabricated design**. There are no assembly photographs, hardware measurements, or physical test results in the supplied archive. The Gerber files are supplied exports and should be regenerated and checked against the Altium project before any fabrication order.

## Saved design rule check

The later DRC report in the supplied project's output folder is dated **13 September 2026, 20:49:57**. It reports **153 violations detected and 0 waived**:

| Rule | Violations | Review needed |
|---|---:|---|
| Hole size | 4 | Four 3.2 mm mounting holes exceed the saved rule's 2.54 mm maximum. Confirm the intended mounting-hole specification and adjust the rule or design. |
| Minimum solder mask sliver | 139 | Check the mask openings and the selected fabricator's capabilities, especially around fine-pitch parts and vias. |
| Silkscreen to solder mask clearance | 10 | Inspect and move or adjust affected legend features. |
| **Total** | **153** | No violations were marked as waived in this report. |

The same report lists **0** clearance, short-circuit, and un-routed-net violations. That does not establish electrical or manufacturing correctness. An older DRC report also existed in the archive; this package includes the later report to keep the review baseline clear. The Gerber export status report was generated later on the same date, at **21:15:01**, so rerun DRC and regenerate all outputs from the final source before using them for production.

## Project dependencies

`AltiumSTM32.PrjPcb` refers to `Schematic-Lib-PhilsLab.SchLib` and `Footprint-Lib-PhilsLab.PcbLib` by relative paths outside the supplied folder. Those third-party library files were not included in the archive and are not redistributed here. Altium may prompt for the libraries when updating components or footprints.

The board images are generated from the provided Gerber data, and the small schematic overview comes from Altium's saved preview. They are **design visualizations**, not photographs of assembled hardware.
