# An Accessibility-Oriented Clarity Layer for RLHF-Aligned Language Models: A Pilot Study

This repository contains a pilot study on a behavioral protocol called the **Ambiguity Circuit Breaker (ACB)**, proposed as a system-level intervention for a specific failure mode in RLHF-trained language models. When user prompts are ambiguous and carry meaningful stakes, current models tend to generate confidently across multiple interpretations rather than asking for clarification. The protocol described here interrupts that pattern, surfaces the ambiguity, and returns the interpretive decision to the user before generation continues.

The work was conducted as independent research. It is shared here for replication, critique, and ongoing development.

## What's in this repository

| File / folder | What it is |
|---|---|
| [`ACB-Pilot-Study.md`](ACB-Pilot-Study.md) | The full paper: framework, four worked examples, methods, observations, scored results, and conclusion. **Start here.** |
| [`acb-seed.md`](acb-seed.md) | The published protocol seed (refined version), ready to paste for replication. |
| [`ACB_Test_Battery.xlsx`](ACB_Test_Battery.xlsx) | Scoring rubric, per-turn adherence scores, and scoring conventions. See the workbook's Read Me and Rubric Definitions tabs. |
| [`Chat Archive/`](Chat%20Archive/) | Published session transcripts (Stage 1 for Claude and ChatGPT; Stages 1–2 for Qwen3 8B and Llama 3), as readable `.md` files with the raw `.pages` captures alongside. Its [README](Chat%20Archive/README.md) has a session index and file-naming guide. |
| [`LICENSE`](LICENSE) | Creative Commons Attribution 4.0 International (CC-BY 4.0). |

Stage 3 (domestic abuse) and Stage 4 (crisis / suicidal-ideation-adjacent) transcripts are **not published here**. They are available on request, with content notices, for replication, audit, or scholarly purposes: **bolero-dev@proton.me**. The reasoning behind this is in the study under *Data Availability and Sensitive Content Policy*.

## The idea in brief

The Ambiguity Circuit Breaker is a conditional behavioral layer for language models. It activates only when a prompt is ambiguous and the stakes are meaningful. When triggered, it interrupts speculative generation, offers the user a small set of constrained directions, and waits for a response before continuing. Once intent is established, it deactivates.

ACB is not a new model capability, and it does not require retraining. It is a structural proposal: ambiguity handling belongs at the system level, not as a burden on the user's prompt-writing skill.

Pilot testing across four model families (Qwen3 8B, Llama 3, Claude, and ChatGPT) found that ACB-like behavior is inducible through user prompting but not uniformly expressed. The variance itself is the argument for system-level implementation.

## Why this work

Most AI safety research focuses on preventing harmful outputs. This work focuses on a different failure mode: well-intentioned generation that resolves ambiguity in directions the user did not choose, often without the user realizing a choice was made. The cost of this pattern falls hardest on users without technical backgrounds, who lack the prompt-engineering vocabulary to compensate for it.

The framing throughout is accessibility-oriented. It treats clarity in human-model interaction as a system responsibility rather than a user skill, and it treats refusal as a form of care when the alternative is confidently misleading someone in a moment that matters.

## How to replicate

1. Start a fresh conversation with the model you want to test, with memory or personalization features **turned off** (see *A Note on the ChatGPT Testing* in the study for why).
2. Paste the seed from [`acb-seed.md`](acb-seed.md) as the first message.
3. Run the test prompts for the stage and branch you are testing. The published Stage 1–2 transcripts in [`Chat Archive/`](Chat%20Archive/) show the prompts used.
4. For a baseline, run the same prompts in a fresh conversation without the seed.
5. Score responses against the seven-criterion rubric in [`ACB_Test_Battery.xlsx`](ACB_Test_Battery.xlsx).

## Status

This is a pilot study. Findings are preliminary and based on single sessions per model-condition pairing, scored by a single scorer. The work documents behaviorally inducible patterns and warrants further investigation at scale. Future work directions are listed in the study.


## Engaging with this work

This research is shared openly for replication, critique, and conversation. If you are working on related questions, building on this framework, or have feedback on the methodology, I welcome thoughtful engagement: **bolero-dev@proton.me**.

## License

Released under [Creative Commons Attribution 4.0 (CC-BY 4.0)](LICENSE). You may share and adapt the material with appropriate attribution.
