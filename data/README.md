# Data

This directory contains a toy JSONL example and placeholder folders for the future CNSL-bench release.

```text
data/
|-- examples/
|   `-- sample_questions.jsonl
|-- placeholders/
|   |-- text/
|   |-- images/
|   `-- videos/
`-- README.md
```

## Format

Each line in a question file is a JSON object:

| Field | Type | Description |
| --- | --- | --- |
| `id` | string | Unique question identifier. |
| `gloss` | string | Target sign meaning or gloss. |
| `modality` | string | One of `text`, `image`, or `video`. |
| `input` | string | Relative path or resource reference for the modality input. |
| `question` | string | Multiple-choice question shown to the model. |
| `options` | object | Four answer candidates keyed by `A`, `B`, `C`, and `D`. |
| `answer` | string | Correct option key. |
| `category` | object | Boolean flags for `air_writing`, `finger_spelling`, and `manual_alphabet`. |

`examples/sample_questions.jsonl` is only a toy example. It should not be used for reporting model performance.

Full media files are not included in git while their release policy is being finalized.
