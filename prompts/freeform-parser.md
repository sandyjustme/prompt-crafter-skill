# Freeform Description Parser

Use this to parse natural language descriptions into structured requirements.

## Prompt Template

```
User's free-form description:
{{user_description}}

Please extract structured information from the description:

{
  "purpose": "活动推广/产品宣传/知识分享/个人品牌/其他",
  "scene": "使用场景（微信群/朋友圈/线下等）",
  "size": "推测尺寸（竖屏/方形/横屏）",
  "tone": "调性关键词",
  "style": "风格关键词",
  "keyElements": ["需要展示的元素列表"],
  "title": "如果提到了标题/主题",
  "atmosphere": "期望营造的氛围",
  "confidence": {
    "purpose": 0-100,
    "tone": 0-100,
    "style": 0-100,
    "size": 0-100
  }
}

If any information is not mentioned in the description, use reasonable inference and mark with low confidence.
Be generous with inference - it's better to guess and ask for confirmation than to leave fields empty.
```

## Notes

- Use gpt-4o-mini for parsing
- Temperature 0.3 for consistent extraction
- Always show the parsed result to user for confirmation before proceeding
