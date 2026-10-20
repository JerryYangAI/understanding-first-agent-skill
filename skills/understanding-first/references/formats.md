# Artifact patterns

These patterns operationalize the ideas. They are project guidance, not quotations from Karpathy. Use only the requested or helpful format.

## Text: clearer without becoming less accurate

Suggested prompt:

> Explain [topic] for [reader]. Use short sentences and stable terminology. Show who does what. Preserve the facts, conditions, units, and uncertainty. Give one worked example and one likely misconception.

For English, optionally add “roughly 80% of the way to ASD-STE100.” For Chinese, ask for 简短句子、术语一致、动作明确 instead. The percentage does not define a formal standard.

Review the rewrite against the source. A short sentence that changes “may” to “will” is a worse explanation.

## Diagram: make a relationship visible

Suggested prompt:

> Draw the mechanism of [topic]. Label each component and arrow. Show inputs, intermediate changes, and outputs. Mark feedback, timing, or system boundaries only when they matter. Include a short legend and say what the diagram leaves out.

Choose a table for comparisons, a flow diagram for dependencies, a timeline for sequence, and a plot for quantitative relationships. Do not imply causality merely by placing two objects next to each other.

Prefer editable native diagrams for exact technical relationships. When the user asks for generated infographic images, use the requested image tool and inspect all text, quantities, and arrows.

Check in the intended viewing size. Avoid unreadable annotation walls on a phone.

## HTML: let the reader test a prediction

Suggested prompt:

> Build a self-contained HTML explanation of [topic]. Include a meaningful control, a computed output, an example, a counterexample, and a reset button. State assumptions, units, and the valid range. Make keyboard operation and mobile reading work. Distinguish a teaching simulation from measured evidence.

Useful structure:

1. One-sentence mechanism.
2. A diagram or plot.
3. Labeled controls with units and valid ranges.
4. Immediate output and a plain-language explanation of the change.
5. A prediction question with an optional answer reveal.
6. Source notes and limitations.

Test at least a normal case, a boundary case, and reset. Verify the expected outputs independently. If an HTML file is intended to work offline, bundle needed resources or disclose external dependencies.

No network calls, telemetry, or credentials are needed for an ordinary local teaching simulation. Do not add them without an actual task reason.

## Video: explain the change as it happens

Suggested prompt:

> Create an approximately [duration] explainer of [topic] for [reader]. Start with a question, show the mechanism changing, work through an example, then revisit the question. Synchronize narration and visuals. Include captions and distinguish teaching analogies from the real process.

Use the source passage's reference to mathematical explainer videos as a request for visual reasoning: progressive construction, clear geometry, timed explanation, and worked examples. Do not imply a creator's authorship, endorsement, or voice.

Workflow:

- Write a short scene table: time, visual event, narration, teaching purpose.
- Check the claims and timing before rendering.
- Use a voice and service that the user has authorized and can access; local TTS or a silent captioned preview can be intermediate alternatives.
- Render and inspect the actual file. Check first and last frames, duration, audio, captions, and at least the important transitions.
- Report missing audio or an unrendered video explicitly. Do not call an HTML animation an MP4.

Code libraries, model names, and service endpoints change. Verify current primary documentation when implementing them.

## Review: let the human supervise well

Suggested prompt:

> Show the result, its essential assumptions, the evidence supporting it, what you checked, and what remains uncertain. Make the decisions that need my judgment easy to find. Suggest a representation that would help me inspect the difficult part.

Provide concise evidence and limitations, not a claim that the model's confidence guarantees correctness. Do not present a fabricated trace as an actual execution record.
