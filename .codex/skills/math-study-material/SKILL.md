---
name: math-study-material
description: "Create or extend conceptually rigorous study guides and worked solutions for the Math 1227 question archive. Use for requests to teach, solve, or prepare study material from a paper in this repository."
---

# Math Study Material

Build study material that lets the student solve a related problem independently, not merely copy a solution.

## Repository map

- Questions live in `questions/<year>.md`.
- Reusable notes live in `study/concepts/`.
- Question-specific guides live in `study/<year>/`.
- Raw scans live in `sources/`; consult them if a question is marked `[Source-faded]` or its transcription is ambiguous.

## Reuse before writing

Before creating a guide, inspect the relevant question and the existing concept notes. Reuse and link to an existing note when it already explains the prerequisite. Extend that note only when the new question needs a missing, reusable idea. Do not duplicate the same prerequisite explanation in several question guides.

Create a new concept note only when the idea is likely to recur or needs a self-contained explanation to make the requested guide understandable. Use a focused, descriptive filename.

## Clarification questions

When the student asks a clarification question, answer it directly and inspect the relevant concept note before editing it.

- Add the explanation when it is a foundational idea, resolves a likely misconception, or will help with later questions.
- Do not add a separate note for a trivial question or duplicate an explanation that is already sufficient.
- If the idea already exists but is hard to understand, improve that existing explanation rather than creating a parallel one.
- Point the student to the exact concept note and section that now contains the explanation.
- Do not change unrelated study files in response to a clarification question.

## Guide design

For each requested question or sub-question:

1. State what the question is testing and identify the cues in its wording.
2. Explain the prerequisite concepts intuitively, with a small example when that improves understanding.
3. Give a concise “solve it yourself” checklist before revealing the answer.
4. Provide a detailed derivation, including substitutions, algebra, sign conventions, and a final check.
5. Call out common mistakes only when they are relevant to that problem.

Prefer a hybrid structure: keep reusable material in `study/concepts/`, then give the question-specific reasoning and answer together in the guide. Link concepts at the top of each guide.

## Revision formulas

In concept notes, visually highlight every formula that is directly used to solve an archive exam question. Use a Markdown callout beginning `> [!IMPORTANT]` and label it `Exam formula` immediately before the formula. Do not box routine intermediate algebra or formulas included only for background; the highlights are for quick revision after the syllabus is complete.

## Mathematical integrity

- Preserve the paper’s wording and notation in the question statement.
- Define every non-obvious symbol before using it in an explanation.
- State assumptions and domains that affect correctness (for example, excluding a singular point or choosing an orientation).
- If the source is ambiguous, say so and explain the interpretation used; do not silently invent notation.
- Verify final answers by substitution, differentiation, geometry, orientation, or another appropriate check.

## Archive maintenance

- Update `README.md` when a new entry-point study guide is added.
- Keep concept notes cumulative: future material should strengthen and cross-link this library rather than replace it without reason.
- Do not alter raw sources or unrelated question transcriptions while preparing study material.
