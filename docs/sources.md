# Sources and attribution

[Back to the project](../README.md)

My work here is primarily curation: bringing public references into one coordinate convention, comparing their labels, retaining the evidence and producing readable exports and reusable connector symbols. This is not a claim to have independently reverse-engineered or bench-verified every contact.

## Primary references

### Brian Benchoff — physical connector investigation

[Reverse Engineering the NVIDIA SXM2 Socket](https://bbenchoff.com/pages/SXM2PCIe.html)

The workbook uses Benchoff's connector-A measurements and chosen physical viewing convention as its coordinate anchor. His work provides the PCIe/power/reset reference and investigation of the K18/K19 circuitry. His minimal single-GPU carrier does not populate the NVLink connector and leaves optional contacts unused.

Credit for those measurements and the original investigation belongs to Brian Benchoff.

### mtf electronics studio — complete interface mapping

[SXM2 to PCIe project family](https://oshwhub.com/mtf-electronics-studio/sxm2-to-pcie)

The workbook uses the normalized mtf definitions for the complete six-group NVLink contact map and additional sideband labels. Multiple revisions from the same author are treated as one source family, not as independent confirmations.

These are community-derived assignments, with their source labels and qualifications retained in the data.

### xinyuuliu — working dual-V100 implementation

[Dual V100 SXM2 to PCIe / NVLink 200GB project](https://oshwhub.com/xinyuuliu/v100-graphics-card-nvlink200gb-c)

The workbook uses this implementation to compare the circuitry and NVLink contacts that the board actually implements. It records agreement across 128 contacts in complete groups 0, 1, 4 and 5. That partial implementation is not evidence that every optional or unused contact is electrically characterized.

The two- and four-GPU guides retain the distinction between demonstrated pairing families and the expanded arrangements proposed here.

## Additional references

- [yunxs SXM2 carrier with ESP32](https://oshwhub.com/yunxs/sxm2-zhuan-pcie-jia-esp32): supplementary functional evidence cited by the workbook, not independent physical coordinates for every pad.
- [Amphenol 84740 manufacturer model archive](https://cdn.amphenol-cs.com/media/wysiwyg/files/3d/s84740.zip): model used in the existing local connector geometry preview and the render derived from it.
- [Catppuccin palette](https://catppuccin.com/palette/): Mocha colours used in the visuals, workbook and optional local theme.
- [KiCad](https://www.kicad.org/): schematic and render exports.

The complete workbook source registry is also available as [`data/sources.csv`](../data/sources.csv), with the role and limitations of each reference.

## Reuse and release status

Newly authored hardware design contributions are offered under CERN-OHL-W-2.0. Original documentation, diagrams and workbook presentation are offered under CC BY-SA 4.0. See the [licence scope and full texts](../LICENSE.md) and [third-party notices](../THIRD_PARTY_NOTICES.md). Both selected licences permit commercial reuse with their applicable reciprocal requirements.

Source projects retain their own terms and authorship. Source links and attribution do not replace those terms, and our notices do not relicense upstream designs, manufacturer models or underlying electrical facts. This public edition distributes the curated reference and rendered previews; raw upstream design archives, footprints and manufacturer models are not bundled.

Original third-party design archives are linked rather than copied into this reference kit. The bundled workbook preserves its source notes. The connector-only symbols and documentation are new presentations of the curated mapping.
