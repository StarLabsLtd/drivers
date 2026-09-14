# Windows driver model map

Choose the directory matching the system model, rather than a product name
from a different generation. The SoC identifiers are taken from the firmware
model map.

| System | SoC/platform | Driver directory | Notes |
| --- | --- | --- | --- |
| Star Lite Mk I | Legacy; SoC not verified | [`soc/intel/legacy/starlite-mki`](soc/intel/legacy/starlite-mki) | Retained historical packages. |
| Star Lite Mk II | Apollo Lake | [`soc/intel/apollo-lake/common`](soc/intel/apollo-lake/common) | Includes the ticket-proven optional DPTF package. |
| Star Lite Mk III | Gemini Lake | [`soc/intel/apollo-lake/common`](soc/intel/apollo-lake/common) | Uses the same verified package set as Mk II. |
| Star Lite Mk IV | Gemini Lake Refresh | [`soc/intel/gemini-lake-refresh/common`](soc/intel/gemini-lake-refresh/common) | |
| Star Lite Mk V | Alder Lake-N | [`soc/intel/alder-lake-n/common`](soc/intel/alder-lake-n/common) | Also use the shared ALC269 package below. |
| Star LabTop Mk II | Legacy; SoC not verified | [`soc/intel/legacy/labtop-mkii`](soc/intel/legacy/labtop-mkii) | Retained historical package. |
| Star LabTop Mk III | Kaby Lake | [`soc/intel/kaby-lake/common`](soc/intel/kaby-lake/common) | |
| Star LabTop Mk IV | Comet Lake | [`soc/intel/comet-lake/common`](soc/intel/comet-lake/common) | |
| Byte Mk II | Alder Lake | [`soc/intel/alder-lake/byte-mkii`](soc/intel/alder-lake/byte-mkii) | |
| StarBook Mk V | Tiger Lake | [`soc/intel/tiger-lake/common`](soc/intel/tiger-lake/common) | Also use the shared ALC269 package below. |
| StarBook Mk VI Intel | Alder Lake | [`soc/intel/alder-lake/starbook-mkvi-intel`](soc/intel/alder-lake/starbook-mkvi-intel) | |
| StarBook Mk VI AMD | AMD Cezanne | [`soc/amd/cezanne/common`](soc/amd/cezanne/common) | |
| StarBook Mk VIr2 Intel | Raptor Lake | [`soc/intel/raptor-lake/common`](soc/intel/raptor-lake/common) | Recovered from the previously ticket-only package set. |
| StarBook Horizon | Alder Lake | [`soc/intel/common`](soc/intel/common) | Use the current [`2145:0002` audio package](soc/intel/audio/2145-0002/realtek-6.0.10034.1.zip). |
| StarBook Horizon Plus | Raptor Lake-U | [`soc/intel/common`](soc/intel/common) | Use the current [`2145:0002` audio package](soc/intel/audio/2145-0002/realtek-6.0.10034.1.zip). |
| StarBook Mk VII N200 | Alder Lake-N | [`soc/intel/alder-lake-n/common`](soc/intel/alder-lake-n/common) | Also use the shared ALC269 package below. |
| StarBook Mk VII Ultra 7 | Meteor Lake | [`soc/intel/meteor-lake/common`](soc/intel/meteor-lake/common) and the current [`2145:0002` audio package](soc/intel/audio/2145-0002/realtek-6.0.10034.1.zip) | Use the shared Meteor Lake package set and this audio package. |
| StarFighter Mk II | Meteor Lake | [`soc/intel/meteor-lake/common`](soc/intel/meteor-lake/common) and [`2014:7017` audio](soc/intel/audio/2014-7017/realtek-6.0.9901.1.zip) | Use the shared Meteor Lake package set and this audio package. It supports the Windows legacy `2014:7017` policy; do not substitute the ALC269 current-ID package. |

## Shared packages

| Package | Applicable systems |
| --- | --- |
| [`soc/intel/common/realtek-audio-alc269.zip`](soc/intel/common/realtek-audio-alc269.zip) | Star Lite Mk V, StarBook Mk V, and StarBook Mk VII N200. |
| [`soc/intel/audio/2145-0002/realtek-6.0.10034.1.zip`](soc/intel/audio/2145-0002/realtek-6.0.10034.1.zip) | StarBook Horizon, Horizon Plus / Raptor Lake-U, and StarBook Mk VII Ultra 7 systems whose codec reports `HDAUDIO\\FUNC_01&VEN_10EC&DEV_0269&SUBSYS_21450002`. |
| [`soc/common/goodix-fingerprint-reader.zip`](soc/common/goodix-fingerprint-reader.zip) | StarBook Mk VI Intel and AMD. |

The Realtek 10034 package must not be used for the StarFighter MTL ALC235
`2145:0001` policy. Its device ID is not matched by that package.
