# Third-party notices and source rights

[Project licence and scope](LICENSE.md) · [Technical source credits](docs/sources.md)

The project primarily curates public reference information. Its licences apply to newly authored contributions and rights held by their contributors, not to every upstream reference or factual assignment. Original EDA archives, source footprints and 3D model files are not bundled in this repository.

## Brian Benchoff

- [Reverse Engineering the Nvidia SXM2 Socket](https://bbenchoff.com/pages/SXM2PCIe.html)
- [Source project](https://github.com/bbenchoff/SXM2toPCIe)

Benchoff's article identifies its text as copyright 2025 Brian Benchoff, CC BY-SA 4.0, and describes its hardware design files as “WTFPL 3.0, MODIFIED FOR NERDS”, referring readers to a repository licence. Those statements are recorded as upstream notices, not a blanket grant covering separately supplied third-party models. The reference kit credits his measurements and coordinate convention; it does not reproduce his article or package his board files.

## Community EDA references

- [mtf electronics studio](https://oshwhub.com/mtf-electronics-studio/sxm2-to-pcie)
- [xinyuuliu dual-V100 implementation](https://oshwhub.com/xinyuuliu/v100-graphics-card-nvlink200gb-c)
- [yunxs ESP32 carrier](https://oshwhub.com/yunxs/sxm2-zhuan-pcie-jia-esp32)

Their authors retain their designs and original expression. No licence for their raw design archives has been established by this reference kit. Curated assignments and source labels are retained for traceability; our licence notice does not relicense upstream files or create exclusive rights in electrical facts.

## Manufacturer and source geometry

[Amphenol's s84740 model archive](https://cdn.amphenol-cs.com/media/wysiwyg/files/3d/s84740.zip) supplies the connector model used in the existing local geometry render. The cover's connector shape also uses the local reference footprint's fabrication outline. The cover's geometry and both `connector-render` images are excluded from our blanket CC licence. No separate redistribution licence for the raw manufacturer model is asserted here; verify the applicable source terms before extracting or redistributing it.

The local project also contains a separately obtained SnapMagic 74221 model with terms distinguishing integrated board designs from redistribution of standalone models. That model and its raw footprint are not included here. Those terms are not assumed to license a different Amphenol model or footprint.

`assets/footprint-reference.png` is KiCad's native export of the local dual-connector reference footprint, preserving its source pads and outlines. It shares the supplied SXM2 carrier reference provenance recorded in [the visual notes](docs/visuals.md#render-provenance) and is excluded from our blanket CC licence. The image is included for reference; the raw footprint file is not bundled.

## Catppuccin

The [Catppuccin palette](https://github.com/catppuccin/palette) is copyright 2021 Catppuccin and published under the MIT licence, retained in [LICENSES/Catppuccin-MIT.txt](LICENSES/Catppuccin-MIT.txt). The project uses its Mocha colour values. The optional KiCad theme was assembled from the local editor configuration with those values; the upstream [Catppuccin KiCad integration](https://github.com/catppuccin/kicad) is a separate reference and is not copied wholesale.

## Names and tools

NVIDIA, V100, NVLink, Amphenol, KiCad, Catppuccin and other third-party names identify the products, references or tools involved. They do not imply endorsement or transfer trademark rights. KiCad-generated schematic previews depict our connector symbols and placements; third-party model geometry is identified separately above.
