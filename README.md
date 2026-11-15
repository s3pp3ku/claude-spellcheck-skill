# Spellcheck skill for Claude Code

A Claude Code skill that autocorrects spelling, typos, homophones, capitalization and punctuation while keeping your wording and tone. It leaves code, URLs, names and casual spelling alone.

## Install

```bash
git clone https://github.com/s3pp3ku/claude-spellcheck-skill ~/.claude/skills/spellcheck
```

## Use

- `/spellcheck <text>` corrects the text you give it
- `/spellcheck path/to/file.txt` corrects a file and asks before saving over it
- Or ask "fix my typos" or "proofread this" and Claude runs it on its own

You get the corrected text in a copyable block, plus a short list of the changes.
