# GPT Resources

Reusable learning skills that turn real engineering problems into practical,
transferable knowledge. Each skill helps address the immediate problem while
building understanding through evidence, predictions, and small experiments.

## Available skills

| Skill | Use it for |
| --- | --- |
| [Antifragile AI](gpt-skills/learn/antifragile-ai/SKILL.md) | AI experiments, machine learning, linear algebra, LLMs, agent workflows, and general software design. |
| [Antifragile Embedded](gpt-skills/learn/antifragile-embedded/SKILL.md) | Firmware debugging, electronics, hardware–software interactions, timing, concurrency, and embedded system design. |

Choose the skill that matches the problem you want to learn from. Both are
intended for learning requests, rather than routine edits.

## Usage

Open the relevant `SKILL.md` and provide its instructions to your assistant,
along with a concrete problem, code fragment, measurement, or design decision.
For a tool that supports installing skills, use the complete skill folder and
follow that tool's installation instructions. This repository stores the skill
sources; cloning it alone does not install them.

Example requests after making the skill available:

**AI and software**

> Use Antifragile AI to help me understand why my classifier performs well on
> training data but poorly on validation data. Help me choose a diagnostic test.

**Embedded engineering**

> Use Antifragile Embedded to investigate why my UART receiver loses bytes
> under load. Help me connect the measurements to interrupt timing and buffering.

**Interactive practice**

> Use interactive practice: ask for my prediction and wait for my answer before
> revealing the expected result or explaining the mechanism.

Include the expected behavior, observed behavior, available evidence, and any
hardware, time, or budget constraints. The skills use information already in
the conversation and ask focused questions when important details are missing.

## What to expect

- An explanation that distinguishes observations, hypotheses, and conclusions.
- One or two concepts tied to the current problem.
- A useful next diagnostic or design step and a small learning experiment.
- A focused resource or transfer question when helpful.

Teaching adapts to demonstrated knowledge. Interactive practice elicits your
prediction first; other requests can use worked examples. Urgent troubleshooting
takes priority over deeper teaching. Learning records are saved only when
requested or already authorized.

## Repository structure

```text
gpt-skills/
└── learn/
    ├── antifragile-ai/
    │   └── SKILL.md
    └── antifragile-embedded/
        └── SKILL.md
```

Each `SKILL.md` contains a name and activation description in YAML frontmatter,
followed by the learning workflow and its constraints.
