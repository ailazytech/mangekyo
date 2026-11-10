# concept-mining

English ｜ [繁體中文](README.md)

An agent skill that connects an everyday description to established professional knowledge. You have noticed something, hit a problem or want to achieve something, but you do not know what it is called in any field, so you cannot find the research and solutions that already exist. This skill finds the name, the literature and how other fields solved it, and keeps what was verified apart from what is merely similar.

It links sideways and does not decide for you. To turn a topic into a direction and a plan, use [ryoiki-tenkai (Domain Expansion)](https://github.com/ailazytech/ryoiki-tenkai); the output of this skill works as its background input.

The skill and prompt text are written in Traditional Chinese; the agent replies in the user's language.

## What it does

| Step | Content |
|---|---|
| 0. Confirm and restate as a mechanism | Confirm the reading; decide whether it is a phenomenon, a problem or a goal; strip the surface details and restate it as who, under what constraints, wants what, and where it gets stuck |
| 1. Established terms | Candidate terms from 2–3 different fields (Chinese and English, definition, where it fits, where it does not), each checked by searching the term; says so plainly when no term fits |
| 2. Theory and research | Split into directly relevant research, theories worth consulting, and analogies that are only similar; each with its conditions, limits, and whether it was replicated or overturned |
| 3. Solutions from other fields | What that field calls the problem, how it handles it, what can be borrowed, and which conditions differ so it cannot be copied as is |
| 4. Converge | The terms, theory and cross-field method most worth keeping, search keywords in Chinese and English, one small experiment, and a list of what is still unverified |

Key rules: search before writing; tag every item as verified, from memory or inference, and never attach a link that was not opened; no invented papers, figures or URLs; no coined phrases presented as accepted terms; 2–4 items per step, depth over breadth.

## Four modes

| You say | The agent |
|---|---|
| A description + "概念挖掘", "is there a term for this" or "how do other fields solve it" | Runs the whole process (steps 0–4) and replies in the chat |
| "what is this called" / "quick" | Returns only the mechanism, candidate terms and keywords |
| "give me the prompt" | Returns `prompt.md` so you can paste it into another model or agent |
| "save it" | Runs the whole process and writes `docs/concept-<name>-<date>.md` |

## Install

### Claude Code

Put this folder at `~/.claude/skills/concept-mining` and start a new session.

### Other agents or models

Agents that read `SKILL.md`: put the folder in their skills directory. Others: paste the full or short prompt from `prompt.md`.

## Files

- `SKILL.md`: the skill instructions for agents (steps, rules, output format, how it feeds Domain Expansion)
- `prompt.md`: ready-to-paste prompts (full and short)

The steps are the same in both files; when one changes, change the other too.

## License

MIT
