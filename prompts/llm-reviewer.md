# LLM Reviewer Prompt

Use this when a template was matched but needs quality checking/enhancement.

## Prompt Template

```
Generated prompt:
{{generated_prompt}}

User's special requirements:
{{special_requirements}}

Please check and fine-tune:
1. Does it accurately reflect the tone "{{tone}}"?
2. Are all required elements "{{elements}}" mentioned?
3. Any room for improvement?

If adjustments needed, output the improved prompt.
If it's already good, output "OK".
```

## Notes

- This is a quick check, not a full rewrite
- Use gpt-4o-mini for speed and cost (~$0.003/check)
- Temperature 0.5 for consistency
