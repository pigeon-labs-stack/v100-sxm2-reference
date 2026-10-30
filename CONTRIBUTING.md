# Help improve the V100 SXM2 reference

This project curates public pinout information and editable logical schematics. Corrections, source comparisons, oriented photographs and measured results are useful contributions. You do not need to write code.

## Report a correction

Use the repository's [issue forms](https://github.com/pigeon-labs-stack/v100-sxm2-reference/issues/new/choose). For a pinout or NVLink correction, include:

- The release tag or commit you checked.
- The exact connector and pad, for example **B/E20**, or both GPU/group/pad endpoints for a connection.
- The current entry and your proposed correction.
- Your source link, document location or measurement method and result.
- The physical view, connector identity and any mirroring or rotation. Say when these are unknown.
- Whether the evidence is a direct measurement, a source comparison or an interpretation.

An unused contact in a source design does not establish an official NVIDIA NC assignment. Keep candidate labels and conflicting evidence visible until they are resolved. NVHS group numbers are not assumed to be NVIDIA software Link IDs.

For a broken file or unclear explanation, use the documentation/file form. For broader project conversation, join the [Level1Techs discussion](https://forum.level1techs.com/t/designing-an-open-source-budget-4x-v100-sxm2-nvlink-backplane-passive-pcie-vs-pex8749/250801).

## Propose an edit

Small corrections can be submitted directly as a pull request. Explain what changes and include the evidence above when an electrical assignment or coordinate changes. Describe substantial new circuit or board work in an issue first so its scope can be discussed.

Preserve source credits, original source labels and the distinction between measured, compared and derived information. Keep the CSVs, workbook, KiCad symbols/schematics and affected diagrams consistent when changing a mapping. Call out any copies that still need updating. Record user-visible mapping changes in [CHANGELOG.md](CHANGELOG.md).

The repository contains reference files for users. Local generators and maintenance scripts are not part of the published kit; you do not need a Python environment to open the workbook, read the PDFs or use the KiCad starters.

## Credit and reuse

Retain attribution to the original investigators and source projects. Submit material you can share under the applicable [project licence](LICENSE.md), and identify any third-party material and its terms. Our licences cover rights held in original contributions; they do not replace upstream terms or claim ownership of pinout facts. See [third-party notices](THIRD_PARTY_NOTICES.md).

## Useful next investigations

Physical connector A/B identity, footprint viewing direction, mating-part selection and the correspondence between physical NVHS groups and software Link IDs remain useful areas for independent confirmation. The [status page](docs/status.md) and [footprint notes](docs/footprint.md) describe what is still open.
