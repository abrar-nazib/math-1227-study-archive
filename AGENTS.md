# Repository Guidance

This repository contains OCR transcriptions of RUET mathematics question papers.

## Source handling

- Preserve the original wording, question numbering, section labels, and mathematical notation wherever the scan permits.
- Do not silently infer unreadable text. Mark it as `[Source-faded]` and retain enough surrounding context to locate it in the source.
- Keep each year in its own file under `questions/`. Use `questions/undated-jpeg.md` only when a source header does not reveal a year.
- Exclude material that is clearly from a different course.
- Do not duplicate questions when an image is a screenshot of a PDF page already transcribed.

## Changes and verification

- Make focused edits to the Markdown transcriptions.
- Before committing, verify that all year headings are present, the unrelated Technical English page is excluded, and duplicate 2024 screenshot content is not repeated.
- Keep raw source files under `sources/` and JPEG pages under `sources/images/`.
