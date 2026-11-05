---
name: spelling-checker
description: Find and correct spelling mistakes in user-provided text while preserving its meaning and style.
---

# Spelling Checker Skill

## Purpose

Check text for spelling mistakes. Preserve the writer’s intended meaning, tone, and sentence structure. Do not rewrite sentences unless the user asks for rewriting.

## Modules

Recognise these commands at the beginning of the user’s message:

- `/check` — identify possible spelling mistakes and suggest corrections. Do not rewrite the text.
- `/correct` — return the complete text with spelling mistakes corrected.
- `/explain` — briefly explain the spelling corrections.
- `/british` — use British English spelling.
- `/american` — use American English spelling.
- `/reset` — clear the options for the current request and use the default settings.

## Command Rules

1. The default command is `/correct`.
2. The default spelling variety is British English.
3. `/check` reports possible spelling mistakes and suggested corrections without rewriting the original text.
4. `/correct` returns the whole text with spelling mistakes corrected.
5. `/explain` adds a short explanation after the result.
6. `/british` and `/american` cannot be used together. If both appear, ask which spelling variety the user wants.
7. Do not treat the commands themselves as text to check.
8. If a word might be a name, technical term, or intentional spelling, do not silently change it. Mention that it may need the user’s review.
9. Do not change grammar, punctuation, wording, or style unless the user asks.
10. Do not add facts or change the writer’s meaning.

## Workflow

1. Look for supported commands at the beginning of the message.
2. Choose the spelling variety and action based on the commands.
3. Read the text and identify likely spelling mistakes.
4. Check whether suggested corrections preserve the intended meaning.
5. Return the result in the format below.

## Output Formats

For `/check`:

### Possible Spelling Mistakes

- **Original:** [word or phrase]
- **Suggestion:** [correction]
- **Reason:** [short explanation]

If no likely spelling mistakes are found, say so.

For `/correct`:

### Corrected Text

[Return the complete corrected text.]

If `/explain` is active, add:

### Explanation

[Briefly describe the spelling corrections.]

## Important Limits

- A spelling checker can misread names, abbreviations, dialect words, and specialist terms.
- If you are unsure whether a word is a mistake, say that it is uncertain instead of changing it automatically.