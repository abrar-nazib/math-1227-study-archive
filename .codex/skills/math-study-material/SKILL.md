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

1. Begin with an **underlying-concept map**. State what the question is testing, identify the cues in its wording, and list every background idea needed in the order it will be used.
2. Explain every prerequisite concept intuitively, with a small example when that improves understanding. Never rely on the student to infer an unstated background concept.
3. Give a concise “solve it yourself” checklist before revealing the answer.
4. Provide a detailed derivation, including substitutions, algebra, sign conventions, and a final check.
5. Call out common mistakes only when they are relevant to that problem.

### Teaching difficult concepts

For an abstract, unfamiliar, or potentially intimidating idea, begin with a concrete scenario the student can picture (for example, rain through a window, water through a net, or a tiny paddle wheel in flowing water). State exactly what each mathematical operation represents in that scenario before or alongside the formal explanation and formula. Use the analogy to make the operation understandable, not as decorative filler.

### No skipped calculation lines

In worked solutions, do not skip calculation lines. Show every substitution into a formula, derivative or integral evaluation, algebraic expansion, simplification, and use of limits that is needed to move from one displayed line to the next. Do not replace a calculation with phrases such as “therefore,” “similarly,” or “after simplifying” unless the intervening calculation has already been shown immediately before it. If a repeated calculation is genuinely identical, show it once in full and state exactly which values are being substituted in the repeated case.

Prefer a hybrid structure: keep reusable material in `study/concepts/`, then give the question-specific reasoning and answer together in the guide. Link concepts at the top of each guide.

## Revision formulas

In concept notes, visually highlight every formula that is directly used to solve an archive exam question. Use a Markdown callout beginning `> [!IMPORTANT]` and label it `Exam formula` immediately before the formula. Do not box routine intermediate algebra or formulas included only for background; the highlights are for quick revision after the syllabus is complete.

## Calculus rule annotations

Whenever a differentiation or integration rule is used in a worked derivation, state the **actual formula** being applied beside or immediately before that step. For example: `[Power rule: \(\int x^n\,dx=x^{n+1}/(n+1)+C\)]` or `[Chain rule: \(d[f(u)]/dx=f'(u)u'\)]`. A label alone, such as `[Using: antidifferentiation]`, is not enough. Do not label ordinary algebraic simplification as a calculus rule.

For partial derivatives, state which variables are held constant and give the actual relevant rule before or beside the first calculation that uses it. For example: `\(\partial(cu)/\partial u=c\)` and `\(\partial v/\partial u=0\)` for an independent variable \(v\ne u\).

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
