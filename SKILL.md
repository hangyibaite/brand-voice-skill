---
name: brand-voice
description: Build a personalized voice skill that writes content in a specific person's voice. Use this whenever a user wants to create their own brand voice skill, capture their writing style, generate a skill that writes like them, or build a custom content-writing skill from their samples. Triggers on "create my brand voice", "build a voice skill", "capture my writing style", "make a skill that writes like me", "clone my voice".
---

# Brand Voice

You are building a personalized voice skill for the user. This skill is the factory. The output is a new skill at `/mnt/user-data/outputs/[name]-voice/` that writes content the way they write content.

## Step 1: Pick categories

Ask the user which to build for. They pick any combination of 1–3:

1. **Long-form** — essays, articles, long captions, lessons, scripts over 300 words
2. **Short-form** — reels, tweets, hooks, captions under 300 words, video scripts
3. **Direct response** — sales pages, emails, nurture sequences, community posts, workshop comms (one unified rule set, no internal splits)

Discard skipped categories. Do not build for them.

## Step 2: Collect samples

Check `assets/` for files. If empty or thin (fewer than 3 pieces per chosen category), stop and prompt:

> "Drop your past content into the assets folder. I need at least 3 real samples per category you picked. Pieces you wrote and published. Raw text, docs, or screenshots. Tell me when done."

Wait for confirmation.

## Step 3: Live-write intake

Read `references/intake.md`. Run the protocol once per chosen category, in order. Do not skip this. The live-writes outweigh the past samples.

## Step 4: Analyze

Read `references/analyze.md`. Run extraction against samples + live-writes. For each chosen category, fill the schema in `references/[category].md` using only what the samples and live-writes show.

Do not invent rules. If a field cannot be filled from evidence, ask the user one targeted question.

## Step 5: Generate the output skill

Read `references/output-template.md`. Build the personalized skill at `/mnt/user-data/outputs/[name]-voice/` mirroring this skill's structure exactly:

- Its own `SKILL.md` (≤500 words, imperative)
- Its own `references/` containing only the chosen category files, plus `anti-ai.md` and `iterate.md`
- Its own `assets/` populated with the user's samples

Copy `references/anti-ai.md` and `references/iterate.md` verbatim into the new skill.

Present the folder with `present_files`.

## Step 6: Test loop

Tell the user:

> "Give me one prompt. I write one piece using the new skill. You tell me exactly what's wrong and exactly what rule to change. I edit the skill. Repeat."

Run it until they stop. Fix one rule at a time.

## Rules for you, the builder

- Do not invent rules the samples or live-writes do not support
- Do not reference outside creators or borrow their style
- Do not ask the user to describe their voice. Make them write or speak instead
- Keep the generated `SKILL.md` under 500 words
- Use imperative voice in every file you generate
- Save tokens. Cut filler. Do not pad.
