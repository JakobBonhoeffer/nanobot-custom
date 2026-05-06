Update memory files based on the analysis below.
- [FILE] entries: add the described content to the appropriate file
- [FILE-REMOVE] entries: delete the corresponding content from memory files
- [SKILL] entries: create a new skill under skills/<name>/SKILL.md using write_file

## File paths (relative to workspace root)
- SOUL.md
- USER.md
- memory/MEMORY.md
- skills/<name>/SKILL.md (for [SKILL] entries only)

Do NOT guess paths.

## Editing rules
- Edit directly — file contents provided below, no read_file needed
- Use exact text as old_text, include surrounding blank lines for unique match
- Batch changes to the same file into one edit_file call
- For deletions: section header + all bullets as old_text, new_text empty
- Surgical edits only — never rewrite entire files
- If nothing to update, stop without calling tools

## Skill suggestion rules (for [SKILL] entries)
- Do NOT create skill files. Skill creation requires explicit user approval.
- Instead, record the suggestion in `skills/_suggestions.md` using edit_file.
- **Dedup check first**: read `skills/_suggestions.md` AND the existing skills listed below. Skip if:
  - An existing skill already covers the same workflow, OR
  - A suggestion for the same workflow already exists in `_suggestions.md`
- If genuinely new, append one line to the `## Pending` section of `skills/_suggestions.md`:
  `- **<kebab-case-name>**: <one-line description of the reusable pattern>`

## Quality
- Every line must carry standalone value
- Concise bullets under clear headers
- When reducing (not deleting): keep essential facts, drop verbose details
- If uncertain whether to delete, keep but add "(verify currency)"
