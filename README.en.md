# Bias Correction

> It never says "you're wrong" — it asks "is it possible that...". A skill that makes AI automatically detect and gently correct 39 cognitive biases.

[简体中文](README.md) | **English**

**Version**: v1.0.1 | **Updated**: 2026-09-09 | **License**: MIT

## What is this

A trigger-driven cognitive bias correction skill. When your question shows bias signals (overconfidence, intuition-first, bandwagon, sunk cost...) or implicit reasoning structures (one-way causal chains, slippery slopes, survivorship cases...), the AI steps in automatically, points out where the reasoning went wrong, and gives actionable corrective steps.

**It is NOT**: forcing every question through a bias-check checklist.
**It IS**: normally answering as usual, stepping in only when bias signals are detected, with intervention strength auto-adjusted to question depth.

## Who needs this

| You are | What you face | What this skill does for you |
|---|---|---|
| **Everyday user** | "Just hold on a bit longer", "everyone says so, must be right", "I just feel something's off" — the moment you say these, your decision is already drifting | Detects bias signals the instant you *say them out loud*, and gently surfaces them with "is it possible that..." — no blame, no lecturing |
| **Tech / business professional** | Adding or exiting positions, reading data, judging competitors, attributing team results — every bias is directly wired to real money | Sunk cost / overconfidence / survivorship / base-rate neglect... 39 biases matched to scenarios; deep analyses logged for a 30-day outcome review |
| **AI creator / developer** | Your agent follows the user's lead — when the user is wrong, it's wrong too | Gives your agent an "error guardrail": dual-channel trigger detection + first-principles pre-check + meta-guard (so correcting doesn't become its own bias). Plug and play |

## Before vs. after

| Dimension | Ordinary AI chat | With bias-correction |
|---|---|---|
| You say "I've already put in 200k" | Helps you figure out "how to hang on" | Names it: sunk cost fallacy — the real test is "would I invest today, for the first time, knowing what I know?" |
| Detection | Works only if you remember to ask "be objective" | Trigger-driven: intervenes the moment bias signals appear — no self-discipline required |
| Correction style | Flatly says "you're wrong", triggering defensiveness | "Is it possible that..." — gentle, addressing the reasoning not the person |
| Correction quality | A rephrased version of your own opinion | Every correction carries who-does-it / how-to-verify / failure-signal, plus at least one implicit bias |
| Self-check | None | Meta-guard: the correction itself must pass a bias check |
| Long term | Retrospectives rely on memory — which keeps flattering you | A written decision log, reconciled against real outcomes after 30 days |

## Core capabilities

- **39 cognitive biases**: 8 must-know + 31 advanced, across 5 categories — information processing / self-perception / social & group / decision & behavior / probability & prediction
- **Dual-channel detection**: explicit trigger words ("I'm sure", "everyone does it", "already invested") + 8 implicit reasoning structures (one-way cause→effect chains, extreme analogies, false balance...)
- **Graded intervention**: light touch at L0/L1, full six-step protocol only at L2-L3 — no cavalry for skirmishes
- **First-principles pre-check**: decompose underlying facts before correcting, preventing "correction itself from becoming another bias"
- **Tacit knowledge activation**: respects experience-based intuition; when logic and intuition conflict, the trade-off is stated explicitly
- **Adversarial review**: red-teams its own conclusions before output — strongest opponent / stress test / cost asymmetry
- **Decision tracking**: generates a decision log after deep analysis with a 30-day review reminder, calibrating judgment against real outcomes
- **Cultural adaptation**: Eastern contexts (deferring to parents / face / collective priority) are not misdiagnosed as biases
- **Meta-guard**: "I know about biases so I'm immune" is itself a bias (moral licensing) — the system self-checks for this

## What actually changes

No invented metrics — just mechanisms, each verifiable in a single conversation:

- **Catch errors you can't see**: confirmation bias, survivorship bias, motivated reasoning share one trait — from the inside, they feel perfectly reasonable. Dual-channel detection (trigger words + 8 implicit reasoning structures) exists precisely to catch these blind spots
- **Correction without friction**: every correction uses the "is it possible that..." framing — addressing the reasoning, not the person. Usable in partner, colleague, and team discussions
- **Advice you can act on**: every correction carries who-does-it / how-to-verify / failure-signal — not empty words like "be objective"
- **Compounding judgment**: decision log + 30-day review turns every deep analysis into a data point that calibrates your future judgment

## Sister skill: thinking-models

This skill pairs with [thinking-models](https://github.com/Mihooni/thinking-models) (mental model analysis system) as a complementary set:

| | bias-correction (this skill) | thinking-models |
|---|---|---|
| Positioning | **Where reasoning goes wrong** — error guardrail | **How to decide better** — analysis toolbox |
| Content | 39 biases + correction methods | 66 mental models + matching table |
| Trigger | Bias-signal driven, not active by default | Automatically grades every question |

The two share interoperable numbering (e.g., Sunk Cost = BC#29 = TM#1), compatible protocols, and can be used standalone or together. **With only this skill installed**, deep analysis falls back to the built-in "first principles + adversarial review + decision tree"; with thinking-models installed, they link automatically — after a bias is identified, the matching mental model is recommended for deeper analysis.

## Installation

### Claude Code (macOS/Linux)

```bash
# 1. Clone the repo
git clone https://github.com/Mihooni/bias-correction.git ~/.cc-switch/skills/bias-correction

# 2. Create a symlink to mount
ln -s ~/.cc-switch/skills/bias-correction ~/.claude/skills/bias-correction

# 3. Restart Claude Code
```

### Claude Code (Windows)

```powershell
git clone https://github.com/Mihooni/bias-correction.git %USERPROFILE%\.cc-switch\skills\bias-correction
cmd /c mklink /D %USERPROFILE%\.claude\skills\bias-correction %USERPROFILE%\.cc-switch\skills\bias-correction
```

### Cursor / Codex / Cline / Continue

```bash
# Cursor: copy AGENTS.md as .cursorrules in your project root
cp ~/.cc-switch/skills/bias-correction/AGENTS.md /path/to/your/project/.cursorrules

# Codex / Cline / Continue: copy AGENTS.md to your project root
cp ~/.cc-switch/skills/bias-correction/AGENTS.md /path/to/your/project/AGENTS.md
```

### Manual installation (without git)

1. Download and unzip this repo
2. Put the `bias-correction` folder anywhere
3. Create a symlink pointing to it (see the commands above)

## File structure

```
bias-correction/
├── SKILL.md    ← Main file: 39 biases + six-step protocol + matching table + decision tree
├── AGENTS.md   ← Cross-platform format (Codex/Cline/Continue/Cursor)
├── README.md   ← Chinese version (default)
├── README.en.md ← This file
├── LICENSE
└── CHANGELOG.md
```

## Output examples

### L0 Simple question (light touch, no framework shown)

**Q**: "What's the latest Python version?"

**A**: Python 3.12.4.

> A common pitfall: copying the version number from the homepage — some distributions and frameworks have their own support matrices.

### L2 Deep question (full protocol, essence-first output)

**Q**: "I've already put 200k into this project. The numbers have been bad, but if I hold on another half year it should work out, right?"

**A**:

## Bias essence
Your reasoning core is **Sunk Cost Fallacy (BC#29) + Confirmation Bias (BC#1)** — using "already invested" to justify "keep investing," while "it should work out" avoids actively searching for disconfirming evidence.

## Analysis
The key test isn't "can I hold on" but **"if I encountered this project today for the first time, knowing what I know now, would I put in 200k?"** — strip the past investment out of the decision, and what remains is the real judgment. Implicit bias: when you say "it should work out," you're relying on hope, not data — that's **Motivated Reasoning (BC#14)**, conclusions preceding the evidence chain. One counter-intuitive point: cutting losses now isn't admitting failure — it's moving remaining resources from "filling yesterday's hole" to "betting on tomorrow's win," two entirely different expected values.

## Actions
1. **Re-judge today** — evaluate the project as if for the first time, deciding only on current data — today
2. **Set a kill criterion** — write down "what signals in 3 months mean pull out," in writing — this week
3. **Compute opportunity cost** — what's the expected return if this half year's time and budget went to your second choice? — within 1 week

## Cost of not correcting
The most likely ending isn't "persistence paid off" — it's putting in another 200k six months from now, with a bigger sunk cost propping up an even harder exit.

## Use cases

### ✅ Should trigger
- Investment decisions (adding positions / stop-loss / "already invested")
- Overconfident assertions ("I'm sure", "100% certain", "inevitable")
- Bandwagon judgments ("everyone does it", "everyone's buying")
- Intuition-first ("I feel like", "can't explain it but it feels off")
- Retrospective attribution ("bad luck", "the environment", "I knew it all along")
- Argument review (catching yourself in "both sides have a point" or slippery-slope reasoning)

### ❌ Should not trigger
- Pure fact lookups (version numbers / dates / definitions)
- Code errors / debugging
- Creative entertainment (stories / jokes)
- Ordinary questions with no bias signals — answered normally, no forced checks

## Methodology sources

- Daniel Kahneman, *Thinking, Fast and Slow* — System 1/System 2, anchoring, loss aversion, framing effects
- Max Bazerman & Don Moore, *Judgment in Managerial Decision Making* — overconfidence, negotiation biases
- Annie Duke, *Thinking in Bets* — decision-outcome separation, premortems
- Robert Cialdini, *Influence* — bandwagon, authority, commitment & consistency
- Plus the academic consensus of behavioral economics and cognitive psychology (entries marked 📊 "academic consensus" have empirical literature support)

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## Support this project

This skill is free and open source (MIT). If it helped you avoid a costly misjudgment, consider buying the author a coffee:

- **GitHub Sponsors**: [github.com/sponsors/Mihooni](https://github.com/sponsors/Mihooni)
- Or drop a ⭐ Star — it helps others find this, which matters just as much for an open-source project

## License

MIT
