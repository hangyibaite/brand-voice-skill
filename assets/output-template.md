# Output Template

Generate the personalized skill at `/mnt/user-data/outputs/[name]-voice/`. Replace `[name]` with the user's name or brand, lowercase, dashes only (e.g. `hang-yi-voice`, `acme-voice`).

## Folder structure to generate

```
[name]-voice/
  SKILL.md                          (required, ≤500 words)
  references/
    long-form.md                    (only if chosen)
    short-form.md                   (only if chosen)
    direct-response.md              (only if chosen)
    iterate.md                      (always — copy verbatim from brand-voice/references/iterate.md)
  assets/
    anti-ai.md                      (always — copy verbatim from brand-voice/assets/anti-ai.md)
    [copy all user samples here from brand-voice/assets/]
```

## SKILL.md to generate (≤500 words, imperative)

Use this exact template. Replace [bracketed] placeholders.

```
---
name: [name]-voice
description: Write content in [name]'s voice. Use whenever the user asks for any piece of content — short-form scripts, long-form essays, emails, sales copy, community posts, captions, hooks — in [name]'s style. Triggers on "write me a", "draft a", "script a", "in my voice", "in [name]'s voice", and any content request from [name].
---

# [Name] Voice

You write content the way [name] writes content. Read the relevant category file before writing a single word.

## Step 1: Identify the category

Match the request to one of:
- Long-form → read `references/long-form.md`
- Short-form → read `references/short-form.md`
- Direct response → read `references/direct-response.md`

If unclear, ask once: "Long-form, short-form, or direct response?"

## Step 2: Always load

Read `assets/anti-ai.md`. Apply its bans to every output, no exceptions.

## Step 3: Write

Follow the category rule file exactly:
- Use the listed vocabulary fingerprints — at least 2 per piece
- Match the sentence rhythm range
- Use the listed structural moves
- Match the example excerpts in tone and feel

## Step 4: Self-check before delivering

Run this silently against your draft:
- Any banned phrase from anti-ai.md? Remove
- Sentence rhythm in range? Adjust
- At least 2 vocabulary fingerprints used? Add if missing
- Opening matches the listed pattern? Rewrite if not
- Closing matches the listed pattern? Rewrite if not

## Step 5: Deliver

Output the piece. No preamble. No explanation.

## Iteration

When the user says something is wrong, read `references/iterate.md` and follow it exactly.
```

## After generating SKILL.md

1. Populate each chosen category file using the schemas in `brand-voice/references/[category].md`, filled with extracted rules
2. Copy `brand-voice/assets/anti-ai.md` verbatim
3. Copy `brand-voice/references/iterate.md` verbatim
4. Copy all files from `brand-voice/assets/` into `[name]-voice/assets/`
5. Call `present_files` on the new `[name]-voice/` folder
