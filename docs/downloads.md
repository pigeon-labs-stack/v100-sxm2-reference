# Download and open the reference

[Back to the project](../README.md)

## Choose a version

Use the [v0.1.0-reference release](https://github.com/pigeon-labs-stack/v100-sxm2-reference/releases/tag/v0.1.0-reference) for a named snapshot. Download **V100-SXM2-Reference-v0.1.0-reference.zip** for the complete kit: workbook, CSVs, KiCad projects, PDFs, diagrams, credits and licences. The release also offers the workbook and PDFs individually, plus SHA-256 checksums. See [what changed](../CHANGELOG.md).

For the current development files, use **Code > Download ZIP** on the repository landing page. Extract the archive before opening a project. Release and development ZIPs both keep the shared library paths intact when their directory structure is preserved.

This is a public reference pre-release. A reference pre-release is not a hardware-tested carrier-board release.

## Open a KiCad starter

The projects were generated and checked with **KiCad 10.0.7**. Open their `.kicad_pro` files with that version or a compatible newer version; older KiCad versions have not been checked.

| Starter | Project to open | PDF pages |
| --- | --- | --- |
| One module's A/B connectors | [kicad/V100_Connectors.kicad_pro](../kicad/V100_Connectors.kicad_pro) | 3 |
| Two modules with NVLink data connected | [kicad/2-V100/V100_2GPU_NVLink.kicad_pro](../kicad/2-V100/V100_2GPU_NVLink.kicad_pro) | 7 |
| Four modules with NVLink data connected | [kicad/4-V100/V100_4GPU_NVLink.kicad_pro](../kicad/4-V100/V100_4GPU_NVLink.kicad_pro) | 13 |

Keep the **whole `kicad/` directory** when copying a starter. The two-/four-module projects refer to `kicad/V100_Reference.kicad_sym` in their parent directory. If a library appears missing, first check that the archive was extracted and that this file and each project's `sym-lib-table` are still in place. For reuse in a different project, follow the [KiCad guide](kicad.md#reuse-in-your-design).

Open a GPU sheet, then its connector A/B sheet, to reach the individual contacts. Matching global labels connect the NVLink data pins. Clock, power, ground, PCIe and control contacts remain labelled and unconnected. Read the [external clock requirements](kicad.md#external-clocks-required) before using a starter in a circuit.

## Read without KiCad

These PDFs contain every sheet, with native vector drawings and hierarchical links where supported by the viewer. Catppuccin Mocha editions match the screen previews. Print editions use black lines on white paper. The connector sheets are large format; zoom to read individual pins, or print at a suitable size/tile scale.

| Schematic set | Catppuccin Mocha | White-background print edition |
| --- | --- | --- |
| Single-module connectors | [Open PDF](pdf/V100-Connectors-Mocha.pdf) | [Open PDF](pdf/V100-Connectors-Print.pdf) |
| Two V100s | [Open PDF](pdf/V100-2GPU-NVLink-Mocha.pdf) | [Open PDF](pdf/V100-2GPU-NVLink-Print.pdf) |
| Four V100s | [Open PDF](pdf/V100-4GPU-NVLink-Mocha.pdf) | [Open PDF](pdf/V100-4GPU-NVLink-Print.pdf) |

The [standalone workbook](../workbook/V100-SXM2-Pinout-and-NVLink.xlsx) has its own README, complete tables and source notes. No Python tools or build environment are needed to use the files in this reference kit.

## Footprint availability

The [native footprint image](../assets/footprint-reference.png) is a visual reference. This version does not include a raw `.kicad_mod` or assign a PCB footprint to the symbols. The [footprint notes](footprint.md) explain the source, orientation and mapping questions to resolve before a reusable footprint can be offered.
