# Conyr skills for AI agents

Solana coin and wallet checks for AI agents, answered by Conyr's API: whether a coin is bundled and who is buying it,
whether a wallet is any good, who it is and where its money came from, and who is behind a coin.

## Install

```bash
npx skills add conyrai/conyr-skills
```

One skill only: `npx skills add conyrai/conyr-skills --skill conyr-token-check`

## Try it now

A coin check (BONK here), with no key and nothing to set up besides Node.js 22 or later:

```bash
npx -y conyr-cli token DezXAZ8z7PnrnRJjz3wXBoRgixCa6xjnB7YaB1pPB263
```

Without a key, the tool uses Conyr's shared demo key: an ordinary free key shared by everyone without a key of their
own, which reaches only the two free coin routes. When it is busy, a free key of your own takes a minute.

## The skills

| Skill | Plan it needs | What it answers |
|---|---|---|
| [`conyr-token-check`](skills/conyr-token-check/SKILL.md) | Free, and it works on the demo key. Layer 1 adds holders, liquidity, trades and candles. | Is the buying on this Solana coin coordinated, and who is buying? |
| [`conyr-wallet`](skills/conyr-wallet/SKILL.md) | Layer 2 | Is this wallet any good, who is it, and where did its money come from? |
| [`conyr-coordination`](skills/conyr-coordination/SKILL.md) | Layer 3 | Who is behind this coin, and who moves with this wallet? |
| [`conyr-api`](skills/conyr-api/SKILL.md) | Any | For an agent writing code against Conyr: addresses, plans, the OpenAPI contract, MCP and WebSocket setup, error bodies. |

`conyr-token-check` runs Conyr's command-line tool through `npx` (Node.js 22 or later). The other skills call
`https://api.conyr.ai` with `curl`. The tool: https://www.npmjs.com/package/conyr-cli

## Your own key

1. Sign up at https://conyr.ai/api?utm_source=github&utm_medium=readme&utm_content=conyr-skills (Google, or an email
   you confirm).
2. Create a key at https://conyr.ai/app/profile?tab=api&utm_source=github&utm_medium=readme&utm_content=conyr-skills
3. Set it where your agent runs: `export CONYR_API_KEY=<your key>`

The skills use `CONYR_API_KEY` whenever it is set.

## Plans

Read on 2026-11-17 from https://conyr.ai/api?utm_source=github&utm_medium=readme&utm_content=conyr-skills, the place to
check them again. Each paid plan includes everything in the plans listed before it.

| Plan | Price a month | Billed yearly, a month | REST calls a minute | WebSocket connections |
|---|---|---|---|---|
| Free | $0 | | 10 | none |
| Layer 1 | $29 | $23 | 100 | 5 |
| Layer 2 | $75 | $60 | 300 | 20 |
| Layer 3 | $149 | $119 | 600 | 50 |

Platform Feed, $399 a month: every realtime push channel and Layer 3 API access, with white-label rights. Enterprise,
from $999 a month: custom limits.
