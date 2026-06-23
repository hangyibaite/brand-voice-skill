# brand-voice

A skill that builds a personalized voice skill for you. You run it once. It studies how you write, extracts your rules, and outputs a new skill that writes content in your exact voice.

## What it does

1. Asks which content categories you want (long-form, short-form, direct response)
2. Prompts you to describe your business and content pillars
3. Asks you to write or speak a piece of content live — in your natural voice
4. Analyzes your live response + any samples you attach
5. Generates a personalized `[your-name]-voice` skill folder with your rules baked in
6. Runs a test loop: writes a piece, you tell it what's wrong, it fixes the rule, repeat

## Supported categories

| Category | Covers |
|---|---|
| Short-form | Reels, video scripts, hooks, captions under 300 words |
| Long-form | Essays, lessons, articles, scripts over 300 words |
| Direct response | Sales pages, emails, nurture sequences, community posts |

Pick any combination. Skip categories you don't need.

## How to use

1. Add this folder to your Claude skills directory
2. Trigger it: *"build my brand voice skill"* or *"create my brand voice"*
3. Attach past content samples to the `assets/` folder before running (min. 3 pieces per category)
4. Follow the prompts

## Folder structure

```
brand-voice/
  SKILL.md                    orchestration entry point
  README.md                   this file
  intake.md                   live-write intake protocol
  analyze.md                  pattern extraction methodology
  assets/
    anti-ai.md                universal banned constructions
    output-template.md        scaffold for the generated skill
  references/
    long-form.md              long-form rules schema
    short-form.md             short-form rules schema
    direct-response.md        direct response rules schema
    iterate.md                iteration protocol (also baked into generated skill)
```

## Output

A ready-to-install `[your-name]-voice/` skill folder that mirrors this structure, populated with your specific voice rules and example excerpts.

## Iterating after generation

The generated skill has a built-in refinement mode. After it writes something you don't like:

1. Tell it the specific line or rule that's wrong
2. Tell it exactly what to change
3. It edits its own rule file and rewrites

Every correction sticks permanently until you remove it.

## Requirements

Claude with skills support enabled.
