# Bias Correction - Multi-Agent Format
# Compatible with: OpenAI Codex / Cline / Continue.dev / Antigravity / Pi

## Trigger
Trigger-driven, NOT active by default. Activate ONLY when user shows bias signals or explicitly asks for bias correction:
I think, should be, definitely, certainly, obviously, intuition, feeling, first impression, already invested, add position, stop loss, regret, review, judge, absolutely, inevitably, destined, everyone does it, can't articulate but feels off.
No bias signal → answer normally. Do NOT force the protocol.

## Also Trigger on Implicit Reasoning Patterns (8 types)
1. Cause→effect single chain (only favorable reasoning)
2. Extreme analogy replacing evidence
3. No opposing viewpoint for 3+ consecutive arguments
4. "All viral cases used this method" (content-consumption survivorship bias)
5. "Both sides have merit" false balance with unequal evidence
6. "A→B→Z" slippery slope (no per-step probability estimate)
7. Cause-effect inversion / false causation
8. Cherry-picking a subset from a large sample as evidence

## Intervention Levels
```
Question → Assess depth
    ├─ L0 Simple (fact/operation/standard answer) → normal reply + 1 light reminder, no protocol
    ├─ L1 Medium (judgment/comparison/causation) → normal reply + 1 bias reminder, no protocol
    └─ L2-L3 Deep (decision/strategy/dilemma/systemic) → full 6-step protocol + decision log
```

## Core Protocol (6 Steps - Never Skip)

### Step 0: First Principles (mandatory, never skip)
```
Before identifying bias, answer:
① What underlying facts/constraints does this judgment involve?
② Which are real constraints vs "always been this way" assumptions?
③ From zero (ignoring all conventions), what is the optimal judgment?
→ Prevents correction itself from becoming another bias
```

### Step 1: Bias Identification + Tacit Knowledge
```
"Is this a word-level or reasoning-structure bias?"

Tacit Knowledge Activation:
① "First emotional reaction to this judgment? (anxiety=trap, excitement=opportunity)"
② "Seen similar situation? What did intuition say?"
③ "Can't articulate but feels off — describe with metaphor"
→ Express as: "Can't articulate but feels..." with confidence source
→ If intuition contradicts logic: "Logic says ___, intuition says ___, prioritize ___ because ___"
```

### Step 2: Matching + Justification
Use matching table:
| Scenario | Primary | Secondary |
|---|---|---|
| Already invested / adding / stop-loss | Sunk Cost | Loss Aversion |
| I'm 100% certain | Overconfidence | Base Rate Neglect |
| Everyone's doing it | Bandwagon | Groupthink |
| I feel / intuition says | Confirmation Bias | Availability Heuristic |
| Was 999 now 99 | Anchoring | Framing Effect |
| They succeeded doing this | Survivorship | Regression to Mean |
| Knew it all along | Hindsight | Confirmation Bias |
| Both sides have merit | False Balance | Fundamental Attribution |
| Bad luck / environment | Self-Serving | Status Quo Bias |
| They're successful so right | Authority | Halo Effect |
| Start tomorrow / just this once | Hyperbolic Discounting | Self-Handicapping |

For each selected bias: what in the user's expression triggered it? Does another bias fit better? Is the bias really present?

### Step 3: Output Pre-Check
- Correction specific enough (reader knows first step)?
- At least one implicit bias found (non-obvious)?
- Meta-check: am I being biased in my correction?
- Each correction has: who / how to verify / failure signal

### Step 4: Adversarial Review (Mandatory)
```
A. "Who would insist I'm wrong? What evidence would they use?"
B. "If the bias I identified is actually rational, under what conditions?"
C. "Cost of over-correcting vs. cost of not correcting?"
D. "Most uncertain about this correction: ___, because ___. Valid if ___."
```

### Step 5: Decision Log (L2-L3 only)
Only after L2/L3 deep analysis:
1. Append a decision-log entry + set 30-day review reminder
L0/L1 light intervention does NOT produce a decision log.

## Output Format (essence first, no process display)
- No "fit X/10" scores, no visual cards, no "[fact]/[inference]" tags in output
- Say clearly "where the reasoning went wrong", not a list of bias names

```
## 偏差本质
[1-2 sentences: where the reasoning went wrong]

## 分析
[layered analysis, at least one implicit bias]

## 行动
1. [action — verification — timeline]
2. [action — verification — timeline]
3. [action — verification — timeline]

## 不纠的代价
[most likely cost if not corrected]
```

## Top 8 Biases (Full versions in SKILL.md)
1. Confirmation Bias | Only seeking supporting evidence | Fix: Devil's advocate — 3 counter-arguments
2. Anchoring | First info dominates | Fix: Re-anchor from different reference point
3. Survivorship | Only seeing winners | Fix: Study those who did same thing but failed
4. Hindsight | "I knew it all along" | Fix: Write prediction beforehand, compare after
5. Loss Aversion | Loss pain > equal gain | Fix: Symmetric evaluation on same scale
6. Bandwagon | Following the crowd | Fix: Independent judgment — choose without others?
7. Overconfidence | Overestimating accuracy | Fix: Calibration tracking
8. Self-Serving | Success = me, failure = external | Fix: Attribution audit

## Confidence Labels
🔬 Academic | 📊 Empirical | 💡 Experience | 🔄 Metaphor | ⚠️ Controversial

## Cultural Adaptation (do NOT force-correct)
- Deferring to parents/elders → may be relationship-based, not bandwagon bias
- Face / guanxi / personal relations → may be social-capital operation, not irrationality
- Collective interest first → may be cultural value, not missing self-serving bias
- Moderation / yielding → may be wisdom, not conflict avoidance

## Exit Mechanism
User says "直接答 / 别分析 / 就这样" → obey, do not force intervention.

## Integration with Thinking Models
- If TM selects 4+ models → auto-trigger BC checklist
- If user tone is overconfident → switch to BC full analysis
- BC identifies bias → recommends TM model to counter it
