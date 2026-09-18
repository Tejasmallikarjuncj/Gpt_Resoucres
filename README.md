# GPT Resources

A collection of reusable GPT skills for learning and engineering work.
The Antifragile learning skills turn practical problems, debugging sessions,
and experiments into deeper understanding and transferable knowledge.
Interactive learning trees help track concepts, connections, and evidence
of what you can apply independently.

## Learning skills

| Skill | Focus | HTML template |
| --- | --- | --- |
| [Antifragile AI](gpt-skills/learn/antifragile-ai/SKILL.md) | AI, machine learning, mathematics, and software design | [AI learning tree](gpt-skills/learn/antifragile-ai/references/learning-tree-template.html) |
| [Antifragile Embedded](gpt-skills/learn/antifragile-embedded/SKILL.md) | Firmware, electronics, and embedded engineering | [Embedded learning tree](gpt-skills/learn/antifragile-embedded/references/learning-tree-template.html) |

## Learning trees

Each skill includes a self-contained HTML template with embedded CSS and
JavaScript. The templates provide:

- Subject branches, prerequisite references, and branch filtering.
- Selectable nodes with explanations, session sources, evidence, related
  concepts, a small exercise, and a completion criterion.
- Four progress states: **Not started ? Introduced ? Practised ? Demonstrated**.
- A recommended next skill with a reason, plus visually distinct proposals.
- Evidence entry, local browser saving, and JSON export/import.

Nodes represent reusable concepts across sessions. For example, debugging
an 80 ms runnable contributes evidence to **Periodic tasks**; the interval
and runnable details belong in the evidence or exercise. Later sessions
extend the same concept node instead of creating a node for each problem.

Demonstrated requires evidence meeting the skill's completion criterion,
such as your own explanation, a completed exercise, or a working implementation.
Discussion or an assistant-generated solution alone does not establish mastery.
The included nodes form a labelled starter tree; they do not represent past
learning or accomplishments.

## Getting started

1. Open the relevant `SKILL.md` for its purpose and learning workflow.
2. Use the skill with a concrete problem, debugging observation, experiment,
   or design decision. Provide available session notes and completed work
   to personalise progress.
3. Copy its HTML template into your learning workspace and open the copy
   in a browser. No build step or server is required.
4. Select a node to inspect its exercise and record evidence. Export JSON
   to keep a portable backup.

GitHub displays HTML source; download the file or use a local checkout to
open the interactive tree in a browser.

## Updating after a session

Share the latest exported JSON alongside the new session evidence so the
next update preserves your progress. Import JSON through the tree to load
an updated record. Import replaces the current record, so export a backup
first. Imports must use the same `treeId` as the HTML file.

For structural changes, edit the `skill-data` JSON block in the copied HTML
without changing the rendering logic. Keep node IDs stable, choose a unique
`treeId` for each personal tree, and increase `revision` after updates. Set
`starter` to `false` once the record is personalised. A newer embedded
revision takes precedence over older browser data; reconcile your latest
export before updating the file.

Browser storage can be cleared or unavailable and is not shared across
devices. Future learning sessions cannot automatically read it; use JSON
exports to carry progress between sessions.

## Structure

```text
README.md
gpt-skills/
??? learn/
    ??? antifragile-ai/
    ?   ??? SKILL.md
    ?   ??? references/
    ?       ??? learning-tree-template.html
    ??? antifragile-embedded/
        ??? SKILL.md
        ??? references/
            ??? learning-tree-template.html
```
