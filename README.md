# X Posts That Get Read

A writing skill for original X/Twitter posts, threads, replies, and content plans. Built for founders, builders, and small accounts that want to share useful ideas in a natural voice.

The skill turns a topic, rough draft, or set of notes into ready-to-use copy with a clear audience, a specific idea, and a payoff worth reading. Its default topics are practical AI, agents, SaaS, distribution, and founder work; you can supply your own audience, subject, and style.

## What it helps with

- **Standalone posts:** Turn observations and notes into distinct posts with concrete value.
- **Rewrites and reviews:** Strengthen hooks, remove filler, and make generic copy more specific.
- **Threads:** Develop an idea through useful examples and a clear progression.
- **Replies:** Add a relevant example, nuance, or answer to an existing post.
- **Bios and pinned posts:** Explain who you help, what you cover, and why someone should follow.
- **Content plans:** Build varied batches and test posting windows using audience context.

The writing guidance favors plain language, useful detail, honest support, and light wit. It avoids fabricated personal stories, repetitive hooks, engagement bait, and promises of guaranteed reach.

## Install in Codex

This is an instruction-based skill. It includes no executable scripts and requires no X API key to draft copy. You need a host that supports agent skills; the commands below also require Git.

### Personal installation

Install it for use across your projects.

**macOS / Linux**

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/shirshag/x-writing-skill.git ~/.agents/skills/write-x-posts
```

**Windows PowerShell**

```powershell
New-Item -ItemType Directory -Force "$HOME/.agents/skills" | Out-Null
git clone https://github.com/shirshag/x-writing-skill.git "$HOME/.agents/skills/write-x-posts"
```

### Project installation

Run this from your project's root to keep the skill within that project:

```bash
git clone https://github.com/shirshag/x-writing-skill.git .agents/skills/write-x-posts
```

Keep the entire skill directory, including `references/`, `agents/`, and `assets/`. The repository name is `x-writing-skill`; the skill's invocation name is **`write-x-posts`**.

Codex detects newly installed skills automatically. If it does not appear, restart Codex. See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills) for discovery locations and invocation details.

## Use it

In Codex CLI or the IDE extension, mention `$write-x-posts` in your prompt. You can also select it from `/skills`. In the ChatGPT desktop app, use `@` to select the installed skill.

### Draft a batch

```text
Use $write-x-posts to draft five posts for solo SaaS founders about
when to automate a workflow. Keep each under 280 characters.
Use a practical, lightly witty voice and give each post a different angle.
```

### Rewrite a draft

```text
Use $write-x-posts to rewrite this for developers building AI agents.
Keep the core point, add a concrete example, and remove generic hype.

Draft: AI agents are changing everything. Every business needs to adopt
them now or risk falling behind.
```

### Turn notes into a thread

```text
Use $write-x-posts to turn the notes below into a six-post thread.
Audience: early-stage founders. Make each post useful on its own.
Use only the experiences and numbers in my notes.

[Paste notes here]
```

### Write a contextual reply

```text
Use $write-x-posts to write three possible replies to this post.
Add a practical example or useful nuance. Keep each to two sentences.

[Paste the parent post here]
```

For better results, include your audience, goal, source material, preferred voice, and any length limit. Supply real experiences if you want first-person copy. Without a specified batch size, the skill defaults to five distinct standalone posts.

## How it handles algorithm claims

The skill separates writing advice from claims about X's ranking system. Its [evidence ledger](references/algorithm-evidence.md) records a dated snapshot from November 7, 2026, distinguishes inspected defaults from unverified supplied claims, and explains what needs to be checked again.

Treat that ledger as historical context. Volatile platform details need fresh primary-source verification before being presented as current. Ranking coefficients are not points per like, and the skill does not calculate reach scores or promise growth.

The skill produces drafts by default. Publishing, scheduling, replying, or changing a profile requires an explicit request and a suitable connected tool; this repository does not include a posting integration.

## Repository contents

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Main workflow, writing standards, and delivery checks |
| [agents/openai.yaml](agents/openai.yaml) | Display metadata, default prompt, and invocation policy |
| [references/editorial-patterns.md](references/editorial-patterns.md) | Post structures, examples, and repairs for generic copy |
| [references/algorithm-evidence.md](references/algorithm-evidence.md) | Dated algorithm evidence and verification procedure |
| [assets/icon.svg](assets/icon.svg) | Skill icon |

## Customize and update

Edit `SKILL.md` to set your usual audience, topics, voice, and output preferences. Add editorial examples in `references/editorial-patterns.md`. Update the algorithm ledger only with clearly dated evidence and sources.

To update an unmodified personal installation:

```bash
git -C ~/.agents/skills/write-x-posts pull --ff-only
```

In PowerShell, use:

```powershell
git -C "$HOME/.agents/skills/write-x-posts" pull --ff-only
```

For a project installation, use `.agents/skills/write-x-posts` as the path. Commit or back up your local customizations before updating.
