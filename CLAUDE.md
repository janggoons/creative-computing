# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

Teaching materials repository for **창의 컴퓨팅 입문** (Creative Computing Introduction), a 15-week course for art/design students. Content is in Korean. This is a documentation repo — no build system, no test suite.

## File Structure

- `w01/` through `w15/` — weekly lecture materials (source of truth)
  - `wN.md` — Marp presentation source (edit this)
  - `wN.html`, `wN.pdf` — generated exports (do not edit directly)
  - `img/` — supporting images
- `syu/` — mirror of weekly materials adapted for Samyuk University; kept in sync manually but may differ from the main content
- `w04-online/` — online-delivery variant of week 4
- `w13-old/` — archived previous version of week 13
- Semester variants are named with a suffix (e.g., `w13_2024_1st.md`)

## Marp Workflow

All lecture slides are written in [Marp](https://marp.app/) markdown with this frontmatter:

```yaml
---
marp: true
theme: gaia
class: invert
paginate: true
---
```

Export to HTML and PDF using the Marp CLI:

```sh
marp w12/w12.md --html   # generates w12/w12.html
marp w12/w12.md --pdf    # generates w12/w12.pdf
```

The `.md` file is the source of truth. HTML and PDF are generated artifacts.

## Commit Style

Commit messages are written in Korean and describe which week was updated, e.g.:

```
12주차 강의자료 수정
11주차 강의자료 업데이트
```
