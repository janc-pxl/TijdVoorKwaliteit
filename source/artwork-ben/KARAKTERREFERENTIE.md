# Ben — reusable character collection

Six transparent PNG illustrations, generated with the built-in imagegen tool. The welcoming pose is the visual master; all other poses were generated using it and a supplied Ben portrait as identity references.

## Files and uses

- `artwork/ben-welcoming.png` — Welcome: Introductions and the start of an exercise.
- `artwork/ben-thinking.png` — Thinking: Reflection questions and prompts to think.
- `artwork/ben-completed.png` — Exercise completed: Completion and celebration.
- `artwork/ben-worried.png` — Worried: A possible problem or a result to reconsider.
- `artwork/ben-explaining.png` — Explaining: Hints, key points and explanations.
- `artwork/ben-encouraging.png` — Encouraging: Positive feedback and motivation to continue.

## Character design

Keep the same black rectangular glasses, upward styled dark hair, light even stubble without a dense beard patch below the lower lip, charcoal blazer and black polo. Use ben-welcoming.png as the reference for future poses. Maintain the warm ink/gouache treatment and paper grain within the character. Change only the gesture and expression. This first set uses detailed portrait illustration to retain Ben’s likeness.

## Website use

Display around 120–200 pixels wide beside feedback; 220–300 pixels for a welcome or completion panel. Keep height auto and avoid stretching. All assets have transparent backgrounds and can sit on the page’s warm paper background. Keep feedback text as real HTML, separate from the illustration.

```html
<img src="images/ben-thinking.png" alt="" width="160" style="height:auto">
```

Use alt="" when accompanying text already expresses the message; otherwise describe the relevant gesture briefly. Use worried Ben for constructive feedback, paired with a next step. Use the completed pose for finishing an exercise and encouraging Ben for smaller successes.

index.html provides a gallery and individual downloads. PROMPTS.md records the master and variant prompts. Original reference photographs are not redistributed in this package.

