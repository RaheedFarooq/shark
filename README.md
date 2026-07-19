# 🦈 Shark

A **brutally honest product/idea evaluator** for [Claude Code](https://claude.com/claude-code).

Hand it a description of your product, app, startup, or feature — what it is, how
it works, how it's marketed, and where it stands — and Shark gives you the read you
can't get from friends, cofounders, or a cheerleading AI: an up-front verdict, a
scored scorecard, an unfiltered teardown, a market-fit gut check, and a plan for
where to actually spend your effort.

It asks a couple of sharp clarifying questions first, then delivers:

- **A verdict up front** — your concept score vs. your execution score, and the one
  sentence that captures the gap between them.
- **A scored ASCII scorecard** — every dimension rated out of 10 (concept,
  execution, market & growth, overall).
- **The honest read** — what's genuinely strong and worth protecting, and what's
  structurally broken no amount of polish will fix.
- **Market critique** — is your audience the right one, or is there a better one?
- **Recommendations ranked by impact-per-effort** — what to focus on first, and
  what to ignore.
- **The call** — an "I'm in / I'm out" verdict and one concrete next step.

```
CONCEPT
Core insight                                    ████████▌░  8.5
Originality vs. alternatives                     ███████░░░  7.0
Audience appeal                                  ██████▌░░░  6.5
...
OVERALL
Today                                            ██████░░░░  6.0
Achievable ceiling (2–3 iterations)              ████████░░  8.0
```

---

## Install

### Option A — Manual (simplest, cleanest invocation)

Copy the skill into your personal skills folder:

```bash
git clone https://github.com/RaheedFarooq/shark.git
cp -r shark/skills/shark ~/.claude/skills/shark
```

Or for a single project only, copy it into that project's `.claude/skills/`:

```bash
cp -r shark/skills/shark /path/to/your/project/.claude/skills/shark
```

Restart Claude Code (or start a new session) and it's available. This path gives
you the clean invocation: **`/shark tank`**.

### Option B — Plugin (one-command install + updates)

Add this repo as a marketplace and install the plugin:

```
/plugin marketplace add RaheedFarooq/shark
/plugin install shark@shark
```

Installed as a plugin, the skill is namespaced, so you invoke it as
**`/shark:shark tank`** — or just describe what you want in plain language (see
below), which works either way. The upside of this path is easy updates via the
plugin manager.

---

## Usage

Trigger it by slash command **or** plain language — you don't need to memorize a
syntax.

```
/shark tank
<paste your product / idea document>
```

Natural language works just as well:

> **shark tank this idea:** a mobile app that turns your grocery receipts into a
> monthly nutrition report…

> **roast my startup honestly** — here's the one-pager…

### Modes

| Command | What it does |
| --- | --- |
| `/shark tank` | The full teardown (default). |
| `/shark grill` | Identical to `tank` — an alias. |
| `/shark tank focus on monetization` | Full teardown, weighted toward the money question. Any trailing text is treated as a focusing instruction. |

---

## How it works

1. **Clarify** — Shark asks 2–4 questions whose answers actually move a score
   (who the user is, how you'd reach them, what success means to you). Say
   *"just evaluate"* to skip straight to the review.
2. **Score** — every relevant dimension gets a number out of 10, with a reason.
3. **Teardown** — verdict, scorecard, concept-vs-execution read, market critique,
   tiered recommendations, and the final call.

The guiding principle: separate the **concept** from the **execution** and name the
gap between them — because that gap is the part you can act on.

---

## Compatibility

Built for **Claude Code**, using Anthropic's [Agent Skills](https://code.claude.com/docs/en/skills)
(`SKILL.md`) format. `SKILL.md` is an Anthropic format and is **not** compatible
with OpenAI Codex or other assistants — running it elsewhere would need a separate
port.

No registration is required to use or share it: the manual copy and the
`/plugin marketplace add` route both work straight from this repo.

## License

[MIT](./LICENSE) © Raheed Farooq
