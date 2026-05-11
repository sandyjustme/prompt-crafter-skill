# Prompt Optimizer Skill

A Claude Code skill for generating optimized image generation prompts.

## What It Does

Helps users create high-quality prompts for AI image generation tools (DALL-E, Midjourney, Flux, 通义万相, 即梦, etc.) through three easy modes:

1. **Guided Q&A** - Answer 7 simple questions
2. **Free Description** - Describe what you want in natural language
3. **Reference Image** - Upload a style reference

## Features

- **Hybrid Intelligence**: Uses templates for common scenarios (fast, free) + LLM for complex requests (high quality)
- **Tolerance for Incomplete Input**: Always generates an "intent prompt" even with missing info
- **Multi-Model Support**: Optimizes prompts for different AI models
- **Template Library**: 6+ pre-built templates that improve over time

## Installation

```bash
# The skill is already installed at:
~/.claude/skills/prompt-optimizer/
```

## Usage

Just ask Claude:
- "Help me create a poster"
- "I need a prompt for generating an image"
- "I want to make a product promotional image but don't know how to describe it"

## Requirements

**Optional**: OpenAI API key for LLM enhancement (skill works without it using templates)

To configure:
```bash
# Edit config.json and add your API key
vi ~/.claude/skills/prompt-optimizer/config.json
```

## File Structure

```
prompt-optimizer/
├── SKILL.md              # Main skill instructions
├── config.json           # Configuration
├── templates/            # Template library
│   ├── index.json
│   ├── product/          # Product promotion templates
│   ├── event/            # Event promotion templates
│   ├── knowledge/        # Knowledge sharing templates
│   └── personal/         # Personal branding templates
└── prompts/              # LLM meta-prompts
    ├── llm-generator.md
    ├── llm-reviewer.md
    └── freeform-parser.md
```

## How It Works

1. User chooses entry mode (Q&A / Free Description / Reference Image)
2. Skill collects requirements
3. Matches appropriate template OR uses LLM to generate
4. Outputs optimized prompt with Chinese explanation
5. Offers quick adjustment options

## Customization

### Add New Templates

Create a JSON file in `templates/{category}/your-template.json`:

```json
{
  "id": "your-template-id",
  "basePrompt": "Your prompt template with {{variables}}",
  "variables": {
    "title": "from_user",
    "style_keywords": "your, keywords"
  }
}
```

Then add it to `templates/index.json`.

### Configure Defaults

Edit `config.json` to change default model, tone, style.

## Tips

- The skill is designed for普通用户 (general users), not professional designers
- Always start with Mode B (Free Description) if you're not sure what you want
- Templates improve automatically based on usage

## Support

Created with Claude Code skill-creator.
