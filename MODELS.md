# Windows driver model map

Choose the directory matching the system model, rather than a product name
from a different generation. The SoC identifiers are taken from the firmware
model map.

| System | SoC/platform | Driver directory | Notes |
| --- | --- | --- | --- |
| Star Lite Mk I | Legacy; SoC not verified | [`soc/intel/legacy/starlite-mki`](soc/intel/legacy/starlite-mki) | Retained historical packages. |
| Star Lite Mk II | Apollo Lake | [`soc/intel/apollo-lake/starlite-mkii`](soc/intel/apollo-lake/starlite-mkii) | Includes the ticket-proven optional DPTF package. |
| Star Lite Mk III | Gemini Lake | [`soc/intel/apollo-lake/starlite-mkii`](soc/intel/apollo-lake/starlite-mkii) | Uses the same verified package set as Mk II. |
| Star Lite Mk IV | Gemini Lake Refresh | [`soc/intel/gemini-lake-refresh/starlite-mkiv`](soc/intel/gemini-lake-refresh/starlite-mkiv) | |
| Star Lite Mk V | Alder Lake-N | [`soc/intel/alder-lake-n/common`](soc/intel/alder-lake-n/common) | Also use the shared ALC269 package below. |
| Star LabTop Mk II | Legacy; SoC not verified | [`soc/intel/legacy/labtop-mkii`](soc/intel/legacy/labtop-mkii) | Retained historical package. |
| Star LabTop Mk III | Kaby Lake | [`soc/intel/kaby-lake/labtop-mkiii`](soc/intel/kaby-lake/labtop-mkiii) | |
| Star LabTop Mk IV | Comet Lake | [`soc/intel/comet-lake/labtop-mkiv`](soc/intel/comet-lake/labtop-mkiv) | |
| Byte Mk II | Alder Lake | [`soc/intel/alder-lake/byte-mkii`](soc/intel/alder-lake/byte-mkii) | |
| StarBook Mk V | Tiger Lake | [`soc/intel/tiger-lake/starbook-mkv`](soc/intel/tiger-lake/starbook-mkv) | Also use the shared ALC269 package below. |
| StarBook Mk VI Intel | Alder Lake | [`soc/intel/alder-lake/starbook-mkvi-intel`](soc/intel/alder-lake/starbook-mkvi-intel) | |
| StarBook Mk VI AMD | AMD Cezanne | [`soc/amd/cezanne/starbook-mkvi-amd`](soc/amd/cezanne/starbook-mkvi-amd) | |
| StarBook Mk VIr2 Intel | Raptor Lake | [`soc/intel/raptor-lake/starbook-mkvi-r2-intel`](soc/intel/raptor-lake/starbook-mkvi-r2-intel) | Recovered from the previously ticket-only package set. |
| StarBook Horizon | Alder Lake | [`soc/intel/common`](soc/intel/common) | Use `realtek-audio-10034.zip` for the supported current ALC269 audio ID. |
| StarBook Horizon Plus | Raptor Lake-U | [`soc/intel/common`](soc/intel/common) | Use `realtek-audio-10034.zip` for the supported current ALC269 audio ID. |
| StarBook Mk VII N200 | Alder Lake-N | [`soc/intel/alder-lake-n/common`](soc/intel/alder-lake-n/common) | Also use the shared ALC269 package below. |
| StarBook Mk VII Ultra 7 | Meteor Lake | [`soc/intel/meteor-lake/starbook-mkvii-ultra7`](soc/intel/meteor-lake/starbook-mkvii-ultra7) | |
| StarFighter Mk II | Meteor Lake | [`Ultra 7 platform packages`](soc/intel/meteor-lake/starbook-mkvii-ultra7) and [`F2 audio`](soc/intel/meteor-lake/starfighter-mkii) | Use the Ultra 7 set except for audio. The F2 audio package supports its Windows legacy `2014:7017` policy; do not substitute the ALC269 current-ID package. |

## Shared packages

| Package | Applicable systems |
| --- | --- |
| [`soc/intel/common/realtek-audio-alc269.zip`](soc/intel/common/realtek-audio-alc269.zip) | Star Lite Mk V, StarBook Mk V, and StarBook Mk VII N200. |
| [`soc/intel/common/realtek-audio-10034.zip`](soc/intel/common/realtek-audio-10034.zip) | StarBook Horizon and StarBook Horizon Plus / Raptor Lake-U systems whose codec reports `HDAUDIO\\FUNC_01&VEN_10EC&DEV_0269&SUBSYS_21450002`. |
| [`soc/common/goodix-fingerprint-reader.zip`](soc/common/goodix-fingerprint-reader.zip) | StarBook Mk VI Intel and AMD. |

The Realtek 10034 package must not be used for the StarFighter MTL ALC235
`2145:0001` policy. Its device ID is not matched by that package.
