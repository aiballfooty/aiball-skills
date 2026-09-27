# AI Ball — football match analysis skill

An [Agent Skill](https://agentskills.io) that lets an AI assistant look up
[AI Ball](https://aiball.samagent.ai/en/?src=gh)'s football match analysis: home / draw / away
probabilities captured before kick-off, the final scores beside them, and the open record of how those
readings have held up — overall, by confidence band, by week and by competition, next to simple
baselines.

It reads AI Ball's public, read-only JSON endpoints. No account, no API key, nothing to run.

## Install

**Any agent that supports skills** (Claude Code, Codex, Cursor, Gemini CLI, Copilot and others):

```bash
npx skills add aiballfooty/aiball-skills
```

**Claude Code, as a plugin:**

```text
/plugin marketplace add aiballfooty/aiball-skills
/plugin install aiball-football-analysis@aiball
```

**By hand:** copy `skills/aiball-match-analysis/` into your agent's skills folder
(`~/.claude/skills/` for Claude Code).

## What to ask

- "What does AI Ball have on today's matches?"
- "How often is aiball.samagent.ai right, and is that better than just taking the favourite?"
- "Show me the Premier League matches it got wrong recently."
- "Which competitions does it cover?"

## What it will and won't do

- Reports all three outcome probabilities together, says when a match is close to even, and puts the
  record next to a favourite-only baseline and a one-in-three baseline.
- Tells you which readings were captured before kick-off by a scheduled job and which were filled in
  from history before the record page launched.
- Readings appear about two hours before kick-off; fixtures further out are not published yet.
- Covers European league and cup football, MLS, Brazilian football, Copa Libertadores and a selection
  of Asian competitions. The Malaysia Super League and Philippine leagues are not covered.
- Does not tell anyone which side to choose and does not discuss money.

## Data and privacy

The skill only sends plain GET requests to `https://aiball.samagent.ai/api/v1/record/…` — the same data
shown on the [open record page](https://aiball.samagent.ai/en/record?src=gh). It sends no personal
information. The site's privacy policy: https://aiball.samagent.ai/en/privacy

## Repository contents

This repository contains documentation only: the skill's instructions (`SKILL.md`), an API reference
and plugin metadata. AI Ball's models and data stay on its own servers.

## Related

- How the model works, the open-ledger rules, and how to report a data error:
  [aiballfooty/aiball-football-data](https://github.com/aiballfooty/aiball-football-data)

## Contact

https://aiball.samagent.ai/en/contact?src=gh

---

For information only. Not advice. 18+. Documentation licensed under [CC BY 4.0](LICENSE).
