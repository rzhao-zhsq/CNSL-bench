# CNSL-bench Data

This directory contains the public metadata for CNSL-bench together with a small set of image and video examples. The metadata aligns Chinese National Sign Language glosses and textual descriptions from the National Common Sign Language Dictionary with image and video filenames through a shared index.

```text
data/
|-- cnsl_bench.json
|-- examples/
|   `-- sample_questions.jsonl
|-- images/
|   `-- five example images
|-- videos/
|   `-- CSY_front_in-1080x1080_out-512x512/
|       `-- five example videos
`-- README.md
```

## Metadata Format

`cnsl_bench.json` is a JSON array containing 6,707 records. Each record is serialized on a separate line within the array and has the following fields:

| Field | Type | Description |
| --- | --- | --- |
| `index` | integer | Unique index shared by the metadata, image, and video. |
| `gloss` | string | Chinese National Sign Language gloss from the National Common Sign Language Dictionary. |
| `description` | string | Textual description of the sign. |
| `image` | string | Image filename derived from the zero-padded index, for example `0354.jpg`. |
| `video` | string | Video filename derived from the same zero-padded index, for example `0354.mp4`. |

Example:

```json
{"index":2728,"gloss":"阿昌族","description":"（一）一手握拳，手背向外，先在左胸部捶一下，再在右胸部捶一下。 （二）一手五指张开，指尖朝上，然后撮合。","image":"2728.jpg","video":"2728.mp4"}
```

## Media Availability

The textual descriptions in `cnsl_bench.json` are included in this release. Because of copyright restrictions, this repository contains only five example images. Access to the remaining images must be requested separately.

The video filenames refer to samples derived from CNSL-DP, introduced in *A Large Dataset Covering the Chinese National Sign Language for Dual-view Isolated Sign Language Recognition*. This repository contains only five processed video examples. To obtain the source videos, please contact the CNSL-DP authors and follow their data-access requirements.

## Video Directory Naming

The example videos are stored in:

```text
videos/CSY_front_in-1080x1080_out-512x512/
```

The directory name records the signer, camera view, and preprocessing configuration:

- `CSY` is the signer identifier used in CNSL-DP.
- `front` indicates that only the front view is used. CNSL-DP provides dual-view recordings, but CNSL-bench uses the front view for this release.
- `in-1080x1080` indicates that each original 1920 x 1080, 60 fps video is cropped around the signer to retain a 1080 x 1080 square region.
- `out-512x512` indicates that the cropped video is resized to 512 x 512 and converted to 24 fps.

## Evaluation Example

`examples/sample_questions.jsonl` contains toy multiple-choice questions illustrating the evaluation schema. These toy examples are not part of the released benchmark records and must not be used to report model performance.
