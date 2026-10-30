# KiCad connector and NVLink starters

[Back to the project](../README.md)

For archive downloads, library-path help and complete schematic PDFs, see the [download guide](downloads.md). The [footprint notes](footprint.md) distinguish the native footprint image from an assignable PCB footprint.

Choose a project in the [KiCad folder](../kicad/README.md), using KiCad 10.0.7 or a compatible newer version:

| Project | Modules / contacts | Connected NVLink data conductors |
| --- | --- | --- |
| [Connector starter](../kicad/V100_Connectors.kicad_pro) | 1 / 800 | None; all contacts exposed for reuse. |
| [Two-V100 starter](../kicad/2-V100/V100_2GPU_NVLink.kicad_pro) | 2 / 1,600 | 192 |
| [Four-V100 starter](../kicad/4-V100/V100_4GPU_NVLink.kicad_pro) | 4 / 3,200 | 384 |

## External clocks required

**The two-/four-GPU schematics provide NVLink data wiring, not a complete working NVLink implementation. An external NVHS reference clock is required on every module.**

| Input on each V100 | Required frequency | Positive pin | Negative pin |
| --- | --- | --- | --- |
| NVLink / NVHS | **156.25 MHz differential** | **Connector B / E20 — NVHS_REFCLK_P** | **Connector B / F20 — NVHS_REFCLK_N** |
| PCIe, a separate clock domain | **100 MHz differential** | **Connector A / E7 — PCIE_REFCLK_P** | **Connector A / F7 — PCIE_REFCLK_N** |

These are the canonical pad assignments and nominal rates recorded in the [pin map](../data/pinout.csv), under `Electrical_Treatment`. The NVHS mapping and clock interpretation are curated from the mtf and working dual-carrier source families; see [source credits and evidence limits](sources.md). They are community reference information, not an official NVIDIA interface specification.

The NVHS input is recorded as **HCSL-class differential**. Select suitable source/fanout circuitry and design its output levels, termination, jitter and distribution for the module; matching frequency alone is insufficient. Use a suitable differential output pair per module, and do not tie clock outputs together. Clock generation, fanout and termination are not supplied by these starter projects. The module also needs its supporting supplies, reset and controls.

For GPU0 the NVHS clock contacts are on **J2**, for GPU1 on **J4**, for GPU2 on **J6**, and for GPU3 on **J8**. The separate PCIe clock contacts are on **J1, J3, J5 and J7** respectively. Pins are labelled and intentionally remain unconnected.

## Single-module connector starter

The single-module root schematic has two child sheets:

- **Connector A / J1:** 400 contacts carrying PCIe, power and control functions.
- **Connector B / J2:** 400 contacts carrying NVLink and related functions.

Each connector has ten symbol units, one per canonical column A–H, J and K. Each unit contains 40 contacts. The arrangement is for readable schematics; it is not a physical footprint drawing.

## Included files

| File | Purpose |
| --- | --- |
| `V100_Connectors.kicad_pro` | Project entry point. |
| `V100_Connectors.kicad_sch` | Root sheet linking to the two connector sheets. |
| `Connector_A.kicad_sch`, `Connector_B.kicad_sch` | Example placement of every contact, with signal names. |
| `V100_Reference.kicad_sym` | Reusable connector symbols with the same pad identifiers and names. |
| `sym-lib-table` | Project-local symbol library registration. |
| `previews/` | Native KiCad SVG exports in the Mocha palette. |
| `themes/v100-mocha.json` | Optional colour theme for the KiCad editor. |
| `2-V100/`, `4-V100/` | Multi-module projects with all A/B contacts and the NVLink data connections. |

The symbols and their graphics were newly generated from the curated workbook; they are not copied SnapEDA or manufacturer symbol drawings.

## Reuse in your design

1. Keep the starter directory together and open the project, or register `V100_Reference.kicad_sym` in your own project's symbol library table.
2. Place `V100_Connector_A` and `V100_Connector_B`. Place all ten units of each connector if you need every contact.
3. Add your own connections, clocking, supplies, reset/control circuits and other supporting hardware.
4. Assign a footprint only after checking connector identity, mating part, pad numbering and physical viewing direction.

Clock, power, ground, PCIe and control contacts retain their names and pad numbers, and remain unconnected. The two-/four-GPU projects connect only the NVLink data contacts. No pins have been marked NC merely to suppress ERC messages. All symbol pins are passive in this reference library: the library preserves the contact map and does not enforce electrical direction or supply rules for your design.

KiCad converts spaces in pin names to underscores. Four connector-B candidate labels therefore appear with `_(candidate)` in the native export; their candidate status is retained, and the CSV/workbook keep the original wording.

**No footprints are assigned.** The physical A/B identity and viewing direction of the existing project geometry remain unverified. Plug and socket parts are not interchangeable choices.

## Two- and four-module starters

Each project has an overview sheet, one child sheet per GPU and separate A/B connector sheets per GPU. Connector references are J1/J2 for GPU0, J3/J4 for GPU1, and so on. All ten units of every connector are placed, exposing all 400 contacts.

Matching **global net labels** join each NVLink TX contact to its peer RX contact. The short label `G0_TX0_L0_P` means **GPU0 / NVHS0 transmit / lane 0 / positive**. The label names the transmitting contact and appears at both ends of that connection. The full signal names remain beside the source and destination pins; the connection CSVs record every endpoint. The reverse direction has its own net, preserving lane number and P/N polarity.

| Label part | Meaning |
| --- | --- |
| `G0` | Transmitting GPU0. |
| `TX0` | Physical NVHS0 transmit group. |
| `L0` | Lane 0 within that group. |
| `P` / `N` | Positive / negative contact of the differential pair. |

The same key appears on every NVLink connector sheet.

Global labels apply throughout a KiCad project. If combining the starters or duplicating an arrangement, add a prefix or rename the labels so separate copies remain electrically separate. Keep the shared parent symbol library or register it in the destination project when reusing sheets.

KiCad netlist exports are compared against every CSV endpoint and against all 800 source pin names for each module. Only the 192/384 intended data nets join multiple pins; all other contacts remain separate. ERC still reports the intentionally unconnected supporting pins. These checks establish digital consistency, not physical routing performance or hardware qualification.

- [Two-V100 overview and NVLink contact preview](../kicad/2-V100/README.md)
- [Four-V100 overview and NVLink contact preview](../kicad/4-V100/README.md)

## Schematic previews

- [Root overview](../kicad/previews/Overview.svg)
- [Connector A, all 400 contacts](../kicad/previews/Connector_A.svg)
- [Connector B, all 400 contacts](../kicad/previews/Connector_B.svg)

Open an SVG at its original size and zoom in to read the individual contacts.

## Licence

Original hardware design contributions are licensed under [CERN-OHL-W-2.0](../LICENSES/CERN-OHL-W-2.0.txt), allowing commercial reuse with the licence’s applicable notice and reciprocal source-sharing obligations. Keep the [licence scope](../LICENSE.md) and [third-party notices](../THIRD_PARTY_NOTICES.md) with redistributed starter files. The licence does not assign rights in upstream geometry, manufacturer models or pinout facts.
