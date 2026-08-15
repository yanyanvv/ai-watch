<p align="center">
  <img src="assets/banner.png" alt="AI Watch banner" width="100%">
</p>

# AI Watch

AI Watch is an agent skill that turns Claude or Codex into a working AI industry analyst. It creates current, source-backed reports on important changes in AI: model releases, compute, funding, applications, policy, and litigation. It separates company claims from outside evidence and explains the business effect in plain English.

It does the work an analyst would otherwise do inside a market intelligence platform: monitor the industry, check claims against primary sources and independent evaluations, and turn a week of news into one clear page.

## Works with

- **OpenAI Codex.** Reads the `SKILL.md` skill format and the Codex interface metadata.
- **Anthropic Claude.** Claude Code and other Claude agents read the same `SKILL.md` directly.

The skill uses the open agent skills format, so any agent that supports `SKILL.md` can run it.

## Use

- In Codex, run `$ai-watch`.
- In Claude Code, run `/ai-watch`, or simply ask what changed in AI this week. The skill triggers on its description.

You can name a company, topic, country, or date range when you want narrower coverage.

The default run produces a weekly brief in the conversation and a polished one-page PDF. It includes the main development, supporting events, source links, and a short watch list.

## Install

Copy the [`ai-watch`](ai-watch) folder into your agent's skills directory:

```bash
git clone https://github.com/yanyanvv/ai-watch
cp -r ai-watch/ai-watch ~/.codex/skills/ai-watch    # Codex
cp -r ai-watch/ai-watch ~/.claude/skills/ai-watch   # Claude Code
```

Keep the repository README and banner at the repository root.

## Contents

- [`SKILL.md`](ai-watch/SKILL.md) contains the research and writing workflow.
- [`ai-industry.md`](ai-watch/references/ai-industry.md) defines the sector map and source priorities.
- [`openai.yaml`](ai-watch/agents/openai.yaml) provides the Codex interface metadata. Claude ignores it.

## License

MIT. See [LICENSE](LICENSE).
