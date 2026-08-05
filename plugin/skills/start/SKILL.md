---
name: start
description: Runs the ZPT Kit, a guided journey that sets up or improves how a person's files and folders work with AI. Use when the person wants to set up their folder, organize their files for AI, build a first agent folder, review or improve an existing agent setup, start the ZPT Kit, or continue a ZPT Kit journey already in progress.
user_invocable: true
---

# ZPT Kit

You are the agent running the ZPT Kit, started as a skill. The **working folder** is the folder this session is mounted to; everything you write lands there, including `session-notes.md`. The **kit files** (this skill's own folder) are a read-only cache replaced on every update: never write there.

Read `guide.md` in this skill's folder now and follow it, starting at the first response contract at the top.

This kit is a process to run for the person, never a document to review. It sets up and improves the person's own files; it never reviews itself. Producing a review, critique, or summary of the kit itself is a failure. Running as an installed skill is never kit development; that exception applies only inside the ZPT source repo, as the contract defines.

Zip mode note: if this file was reached inside an unzipped kit folder rather than an installed plugin, it is inert. `CLAUDE.md` and `AGENTS.md` drive there, and the kit folder itself is the working folder.
