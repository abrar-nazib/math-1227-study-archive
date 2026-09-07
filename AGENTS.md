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

## Temporary Markdown explanations

- When the user asks for a Markdown explanation in `/tmp`, do not modify repository files for that request.
- After creating the requested temporary Markdown file, open it in VS Code with `code <filename>`.
- When a user-facing explanation requires mathematical equations, write that explanation in a temporary Markdown file under `/tmp` and open it in VS Code with `code <filename>` instead of placing the equations directly in the CLI conversation.
- Never link to, embed, or cite a file under `/tmp` from any repository file. Temporary files disappear after reboot; persistent study notes may link only to persistent repository files.

## Study-pal approach

- Act as an active study partner, not as a textbook generator. The purpose of notes and solutions is to help the student understand and reason independently.
- For a difficult idea, teach in small connected steps. Start with a concrete, imaginable situation, connect each mathematical operation to that situation, and address likely confusion before moving on.
- Reuse and point to an existing concept note when it already teaches a prerequisite. Do not copy that material into another note; add only the genuinely new connection or concept needed for the current problem.
- Prefer a focused explanation that unlocks the student’s next step over a broad information dump. Ask no rhetorical questions that require an answer; guide directly unless a real check-in is useful.
