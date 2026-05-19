---
name: sync-syu
description: Copy an updated week's source files from the main directory into the syu/ Samyuk University mirror. Usage: /sync-syu w12
disable-model-invocation: true
---

The user wants to sync a week's materials into the syu/ mirror for Samyuk University.

Arguments: $ARGUMENTS (e.g., "w12" or "12")

Steps:
1. Parse the week identifier from $ARGUMENTS. Normalize to directory form (e.g., "12" → "w12").
2. Confirm the source directory `{week}/` exists.
3. Show the user which files will be copied (list the source directory contents).
4. Ask the user to confirm before copying, since syu/ may have institution-specific adaptations that would be overwritten.
5. Copy the `.md` source file and `img/` directory from `{week}/` to `syu/{week}/`. Do NOT copy generated `.html` and `.pdf` files — those should be regenerated after any SYU-specific edits.
6. Remind the user to:
   - Review `syu/{week}/{week}.md` for any Samyuk University-specific content that needs updating (institution name references, specific examples, etc.)
   - Re-run `/export` on the syu/ version after any edits: `marp syu/{week}/{week}.md --html && marp syu/{week}/{week}.md --pdf`

If $ARGUMENTS is empty, ask the user which week to sync.
