---
name: marp-export
description: Export a week's Marp markdown source to HTML and PDF using the Marp CLI. Usage: /marp-export w12
disable-model-invocation: false
---

The user wants to export a weekly lecture file to HTML and PDF.

Arguments: $ARGUMENTS (e.g., "w12" or "w12/w12.md")

Steps:
1. Parse the week identifier from $ARGUMENTS. Accept formats like "w12", "w12/w12.md", or "12".
   - Normalize to directory form: if given "12", treat as "w12"; if given "w12/w12.md", extract "w12".
   - The source file is `{week}/{week}.md` (e.g., `w12/w12.md`).
2. Verify the source `.md` file exists before running.
3. Run the Marp CLI to export:
   ```
   marp {week}/{week}.md --html
   marp {week}/{week}.md --pdf
   ```
4. Confirm the generated `.html` and `.pdf` files exist after export.
5. Report the paths of the generated files to the user.

If $ARGUMENTS is empty, ask the user which week to export.
If the `marp` command is not found, tell the user to install it with `npm install -g @marp-team/marp-cli`.
