---
name: spellcheck
description: Autocorrect and spellcheck text. Use when the user runs /spellcheck, or asks to fix spelling, typos, grammar, or punctuation in a piece of text, a message, an email, or a file ("spellcheck this", "fix my typos", "proofread", "autocorrect"). Returns the corrected text ready to copy.
---

# Spellcheck / Autocorrect

Fix spelling, typos, and obvious grammar and punctuation mistakes while keeping the writer's voice.

## What to check

- **Text passed as arguments** (`/spellcheck <text>`): correct that text.
- **A file path**: read the file, correct it, and ask before overwriting it (or write the fix if the user already said to).
- **No text given**: correct the user's most recent message or the text they're pointing at.

## Rules

1. Fix: misspellings, typos, doubled or missing words, wrong homophones (their/there/they're, your/you're, its/it's), capitalization at the start of sentences and for "I", missing apostrophes, and clear punctuation errors.
2. Keep: the writer's word choice, tone, slang, sentence structure, and formatting (line breaks, lists, markdown, emoji). Don't rewrite for style unless asked.
3. Leave alone: code, commands, URLs, file paths, email addresses, names, and intentional casual spelling (e.g. "gonna", "lol").
4. If a word is ambiguous, pick the most likely meaning from context and flag it.

## Personal dictionary

If `~/.claude/my-words.md` exists, read it first. Never change a word under "Keep as written", and always fix the entries under "My usual typos". When you spot a new personal word or a typo the user repeats, add it to that file.

## Output

1. The corrected text in a fenced code block so it's easy to copy.
2. A short list of the changes (`teh` → `the`). Skip the list if there were only one or two trivial fixes.
3. If nothing needed fixing, say so in one line.
