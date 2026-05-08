# Claude Code API Cost Estimates

Usage source: https://gist.github.com/parkhc/71373bad6c70b1bf7fd1d3d26b8b5670
Pricing source: https://platform.claude.com/docs/en/about-claude/pricing
Claude Code cost source: https://code.claude.com/docs/en/costs
Generated: 2026-05-08

## Token Mapping

| Cost bucket | Token fields | Tokens |
|---|---|---:|
| Base input | input_tokens | 24,388,228 |
| 5-minute cache write | cache_creation_input_tokens | 1,153,694,213 |
| Cache hits and refreshes | cache_read_input_tokens | 28,776,433,880 |
| Output | output_tokens | 89,259,717 |

## Cohort Cost Estimates

| Model | Standard with cache | Batch with cache | No-cache equivalent | Est. cache savings |
|---|---:|---:|---:|---:|
| Claude Opus 4.7 | $23,952.24 | $11,976.12 | $152,004.07 | $128,051.83 (84.2%) |
| Claude Sonnet 4.6 | $14,371.34 | $7,185.67 | $91,202.44 | $76,831.10 (84.2%) |
| Claude Haiku 4.5 | $4,790.45 | $2,395.22 | $30,400.81 | $25,610.37 (84.2%) |

## Rates Used

| Model | Base input / 1M | 5m cache write / 1M | 1h cache write / 1M | Cache hit / 1M | Output / 1M |
|---|---:|---:|---:|---:|---:|
| Claude Opus 4.7 | $5.00 | $6.25 | $10.00 | $0.50 | $25.00 |
| Claude Sonnet 4.6 | $3.00 | $3.75 | $6.00 | $0.30 | $15.00 |
| Claude Haiku 4.5 | $1.00 | $1.25 | $2.00 | $0.10 | $5.00 |

## Top Users by Estimated Claude Sonnet 4.6 Standard Cost

| User | Estimated cost | Active days | All tokens |
|---|---:|---:|---:|
| user_03 | $2,920.88 | 74 | 6,042,442,130 |
| user_09 | $2,527.82 | 41 | 5,556,442,127 |
| user_10 | $2,277.19 | 44 | 4,826,643,747 |
| user_07 | $2,260.83 | 37 | 5,090,747,383 |
| user_05 | $1,233.67 | 32 | 2,566,141,982 |

## Notes

- Rates are Anthropic Claude API standard global token prices read on 2026-05-08.
- Claude Code charges by API token consumption; model choice affects cost.
- input_tokens are priced as base input tokens.
- cache_creation_input_tokens are treated as 5-minute cache writes because the aggregate export does not split 5-minute versus 1-hour cache creation tokens.
- cache_read_input_tokens are priced as cache hits and refreshes.
- No-cache equivalent re-prices cache writes and cache hits as base input tokens, preserving output-token cost.
- Batch estimates apply a 50% discount to the with-cache token cost, consistent with Anthropic pricing modifiers stacking with Batch API discounts.
- Costs exclude data residency premiums, third-party platform regional premiums, fast mode, web search/code execution fees, taxes, and enterprise discounts.
