# MG-Fusion Sample Dataset

This repository contains a **small illustrative subset**, not the full
training or evaluation corpora used in the MG-Fusion paper.

## Contents

- 26 image-text pairs in total.
- TeaPest-4: 4 classes, 2 pairs per class (8 pairs).
- MDCLD: 9 classes, 2 pairs per class (18 pairs).
- Each text annotation has four fields: lesion, location/distribution,
  extent/range, and leaf state.
- Category names are not included in `diagnostic_text`; supervised labels are
  provided separately in the metadata.
- No held-out test image is included. TeaPest-4 examples come from the
  human-reviewed validation records. MDCLD examples come from the stratified
  quality-control pool and are restricted to train/validation records.
- TeaPest-4 JPEG application metadata (including EXIF/XMP) has been removed
  losslessly; decoded image pixels are unchanged.
- MDCLD images are byte-for-byte copies of the upstream files so that the
  CC BY-NC-ND 4.0 no-derivatives condition is respected.

## Layout

```text
images/teapest4/*.jpg
images/mdcld/*.jpg
metadata/class_map.csv
metadata/samples.csv
metadata/samples.jsonl
checksums.sha256
LICENSES.md
```

## Annotation schema

Each JSONL record contains:

- `sample_id`, `dataset`, `label`, `class_name_zh`, `class_name_en`
- `image_path`, `source_image_id`, `paper_split`
- `caption` (short description)
- `facts.lesion`, `facts.location`, `facts.extent`, `facts.leaf_state`
- `diagnostic_text` (the four fields rendered in the paper input format)
- `source_sha256`, `released_sha256`

## Scope and limitations

This subset is intended for inspection, documentation, and code-format demos.
It is too small for model training, benchmarking, or reproducing the paper's
reported metrics. The source datasets contain acquisition and provenance
limitations described in the paper and project records; this sample does not
remove those limitations.

## Citation

Please cite the MG-Fusion paper when bibliographic details become available.
For MDCLD, also cite:

Yanfang Wang, Guojian Xian, and Ruixue Zhao. "Image-Text Multi-Modal Dataset
of Corn Leaf Diseases based on Manual Annotation and Contrast Generation
Model." *Journal of Agricultural Big Data*, 7(3):371-378, 2025.
https://doi.org/10.19788/j.issn.2096-6369.100060

## Licensing

Read `LICENSES.md` before reuse. Project-owned TeaPest-4 images, diagnostic
text, and metadata are released under CC BY-NC 4.0. Upstream MDCLD images
remain under their original CC BY-NC-ND 4.0 terms.
