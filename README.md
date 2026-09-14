# Star Labs Windows drivers

Windows drivers are organised by processor platform under [`soc/`](soc/).
Use [`MODELS.md`](MODELS.md) to select the exact directory for a Star Labs
model. Do not select packages by a similarly named product generation.

Audio packages with an established target subsystem ID live under
`soc/intel/audio/<vendor>-<device>/`; where more than one version supports an
ID, the archive name includes its `DriverVer` version. Historical generic
vendor bundles retain a codec name until their intended Star Labs subsystem ID
has been verified.

Each ZIP is the vendor package and should be extracted before installation.
Install the chipset package first where one is supplied, then install the
remaining packages for the selected model. Audio packages may require manual
selection from Device Manager when their installer does not bind the device.

The repository keeps one copy of each identical payload. A model may therefore
refer to a shared package in `soc/common/` or another platform directory; the
mapping in `MODELS.md` is the supported source of truth.

`soc/intel/legacy/` contains old systems for which the currently maintained
firmware model map has no SoC identifier. Those packages are retained, but are
not a basis for assigning a driver to a different model.

The Raptor Lake set was recovered from the historical, ticket-only StarBook
Mk VIr2 package. Its Smart Sound Technology package is retained because the
reported missing multimedia-audio controller needs it. Optional HSA and Intel
Graphics Command Center applications are intentionally not included.
