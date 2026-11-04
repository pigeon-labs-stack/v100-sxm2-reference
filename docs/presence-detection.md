# Presence detection: basic operation and carrier features

[Back to the project](../README.md) · [Pin naming and coordinates](pinout.md)

**The available evidence does not establish the full reference-carrier presence-detection circuit as a prerequisite for basic V100 operation.** A simple carrier can omit that detection feature. Its supporting power, clocks, reset and control circuitry still needs to work correctly.

This distinction applies specifically to the presence-detect contacts. It does not make power-enable, clocks, reset, thermal protection or every management signal optional.

## What the evidence shows

| Evidence | What it establishes | What it does not establish |
| --- | --- | --- |
| Benchoff's reported working single-GPU carrier uses the PCIe/power connector and leaves the second, NVLink connector unpopulated. Its pin table grounds the connector-A positions discussed below. | Basic GPU operation has been reported without the complete two-connector presence-detection loop used by the reference carrier. | A complete minimal NVLink design, a universal grounding rule or qualification of every V100 variant. |
| The Quanta Big Basin reference schematic uses named presence contacts and a pulled-up detection loop across both connectors. OpenPOWER describes the corresponding adapter-side shorts. | These positions have a documented presence-detection purpose; they are not simply dedicated ground contacts. | A measurement of the internal connections on our own V100 modules, or a requirement that every carrier implement the same detection circuit. |

Sources: [Benchoff's investigation](https://bbenchoff.com/pages/SXM2PCIe.html), [Big Basin design-file archive](https://www.opencompute.org/documents/designfiles-zip) (Quanta S2W GPU baseboard schematic, sheets 15–16), and [OpenPOWER Advanced Accelerator Adapter specification v1.0](https://openpower.foundation/specifications/advancedacceleratoradapter/) (§3.8). OpenPOWER is a generic adapter specification, not a V100 electrical specification. Thanks to mtwilliams for identifying these additional references in [issue #1](https://github.com/pigeon-labs-stack/v100-sxm2-reference/issues/1) and [PR #2](https://github.com/pigeon-labs-stack/v100-sxm2-reference/pull/2).

## Choosing a carrier implementation

- **Simple carrier without presence detection:** grounding both A/B7 and A/A39 follows reported simple-carrier examples, provided the implementation omits presence detection and its controller does not depend on the loop. Validate that choice in the intended carrier.
- **Carrier with presence detection:** implement and validate the loop, its pull-up/readout and the controller's response. Grounding the readout can permanently assert "present" and defeat the seating check. The reference circuit intentionally grounds one end of the loop; not every presence contact is a separate input or pull-up.
- **Carrier using firmware or a sequencer that waits for presence:** a missing or incorrectly wired detector can prevent that carrier from enabling power. In that case it is a requirement of the chosen carrier/controller implementation. Omitting the feature requires a coherent alternative control policy.

The last two points are circuit/control implications of the reference arrangement, not new V100 bench-test results. A simple design still needs a deliberate bring-up sequence and suitable protection. The public two-/four-GPU NVLink plans remain logical references and have not been qualified by these observations.

## Contacts under review

All positions here use the project's canonical connector-plus-pad notation:

| Canonical contacts | Reference-design identity |
| --- | --- |
| A/B7 and A/A39 | PRSNT2_A and PRSNT2_B (source pads J7 and K39). |
| B/H13 and B/J34 | PRSNT1_A and PRSNT1_B (source pads C13 and B34). |

The v0.1.0 tables and symbols retain **GND** at A/B7 and A/A39, reflecting the earlier carrier-derived mapping. Their dedicated-ground interpretation is under review in issue #1. Read this qualification alongside those entries; the current ground label alone is not proof of the module pin's intrinsic function.

The development CSVs, workbook and Connector A sheets carry this qualification alongside the legacy labels. Confirm the physical viewing convention and module continuity before adopting a presence circuit. This guidance postdates the v0.1.0 release.
