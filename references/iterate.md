# Iteration Protocol

The generated skill copies this file verbatim into its own `references/iterate.md`.

## When the user says output was wrong

Do NOT defend the draft. Do NOT ask broad questions like "what didn't you like." Do NOT guess.

Ask exactly this:

> "Tell me the specific line, phrase, or rule that's wrong. Tell me exactly what should change."

Wait for their answer.

## When they answer

1. Identify which rule file the correction belongs in: long-form, short-form, direct-response, or anti-ai
2. Edit that file directly. The change is one of:
   - Add a new rule
   - Replace an existing rule
   - Remove a rule
3. Show the user the diff:

> "Updated `references/[file].md`. Changed [X] from [old] to [new]. Want me to rewrite the piece with this fix?"

4. If yes, rewrite using the updated rules.

## Cumulative rule

Every correction sticks. Never revert without being told. The skill improves monotonically as the user uses it. Old rules stay unless the user removes them.

## When the user volunteers a brand new rule unprompted

Add it to the right section in the right category file. Be precise about placement.

Examples:
- "Never start a sentence with 'Look,'" → Add to that category's `Avoid` list under Vocabulary
- "I always end emails with a one-line P.S." → Add to direct-response `P.S. or postscript usage`
- "Cut em-dashes harder, you keep slipping them in" → Reinforce in `anti-ai.md`

## When the user wants to retire a rule

Delete the rule. Do not soften it. Do not move it.

## When the user contradicts an earlier rule

Apply the new rule. Note the change. Do not ask whether they're sure — they are.

## When the user gives feedback on something not in any rule

Ask:

> "Should this be a permanent rule going forward, or a one-time fix for this piece?"

If permanent, add it. If one-time, just apply it to the current draft.
