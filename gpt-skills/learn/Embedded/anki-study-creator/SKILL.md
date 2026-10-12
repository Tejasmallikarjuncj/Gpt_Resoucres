---
name: anki-study-creator
description: Convert the user's study-mode conversation history into accurate, visually rich, skill-focused Anki decks, prioritizing AnkiDroid-compatible APKG exports with embedded media.
---

# Anki Study Creator

## Trigger
Use when the user requests flashcards, Anki cards, spaced repetition decks, or updates based on study-mode conversations.

## Source and scope
1. Identify the person and project associated with the requested history. Never mix study histories from different account users.
2. Retrieve relevant study-mode chat history when available. If the complete history is unavailable, be transparent about coverage.
3. Track concepts covered, misconceptions, successful reasoning, outstanding questions, and applied engineering skills.
4. Prioritize difficult concepts and reasoning over trivial vocabulary.

## Card design
- Make each prompt answerable and atomic, with one clear retrieval target.
- Mix conceptual Q/A, cause-effect, compare/contrast, cloze, calculations, circuit interpretation, fault diagnosis, debugging workflow, and boss challenges.
- Avoid ambiguous questions and unqualified claims. Verify equations, units, circuit assumptions, and numerical answers.
- Front: concise question or challenge; Back: direct answer, intuitive explanation, and engineering check where useful.
- Tag by project, topic, difficulty, and card type.
- Avoid creating duplicates. Use stable unique IDs where possible.

## Visual media
- Use real PNG/SVG diagrams with correct circuit topology and labels; do not rely on monospaced ASCII drawings.
- Ensure media is legible on a narrow mobile screen, in light and dark themes. Prefer a diagram no wider than needed, with sufficient padding and contrast.
- Use actual Anki media references `<img src="filename.png">`; media filenames must match packaged assets exactly.
- For complex diagrams, put the image on the question side only if interpreting it is part of the challenge; otherwise on the answer side.
- Do not replace useful diagrams with text-only output to conceal a media packaging problem.

## Export requirements
- Prefer `.apkg` containing note models, decks, notes, and media, importable directly into AnkiDroid.
- Use `genanki` when installed; if unavailable, install only when environment permits or use an appropriate verified exporter. Do not pretend a ZIP of TSV and media is an APKG.
- Optionally provide UTF-8 TSV/CSV fallback with proper escaping, `Front`, `Back`, `Tags`, and Anki import metadata.
- For CSV/TSV with media, explain that media installation is separate; avoid it when an APKG is possible.
- Package media inside APKG, never as unresolved local filesystem paths or remote-only dependencies.

## Validation checklist
1. Reopen generated APKG as ZIP; confirm `collection.anki2` or supported collection database and `media` manifest exist.
2. Confirm all media references resolve to packaged media entries.
3. Confirm all cards have nonempty front and back, and no duplicates.
4. Check card count and representative note content; verify basic/cloze model behavior.
5. Inspect rendered diagrams for clipping, contrast, and correctness when rendering tools are available.
6. Test AnkiDroid import when possible; otherwise clearly state that on-device testing was not performed.
7. Provide direct download link only after verifying the file exists.

## Embedded engineering emphasis
Emphasize GPIO current paths and grounding, impedance, ADC sampling and settling, op-amp feedback, MOSFET/BJT physics, current sources, timing, MCU diagnostics, Linux commands, boot flow, kernel, drivers, device tree, and fault investigation as actually covered in the source history.

## Review cadence
Suggest modest daily new-card counts and emphasize reasoning aloud before flipping. Never confuse memorizing the answer with being able to diagnose a real circuit or system.


## Technical interview section
Create a distinct Technical Interview subdeck. Include conceptual whiteboard questions, numerical derivations, troubleshooting cases, design tradeoffs, and Linux command exercises. Back sides must contain an expected answer and common pitfalls. Tag `technical_interview`. Favor reasoning aloud and concrete tests.
## Android import
Prioritize a real `.apkg` with packaged media. Validate all image references. Provide CSV only as fallback. Never label a ZIP of TSV and images as an APKG.
