# Algorithm evidence and refresh rules

## Provenance

Use this as a dated evidence ledger, not a permanent description of X. The user supplied a third-party algorithm breakdown while requesting this skill on 2026-11-07. Its reference to “yesterday” is relative to the original author; preserve November 5 as an attributed claim rather than shifting it relative to later invocations.

Primary sources inspected during creation:

- Repository overview: https://github.com/xai-org/x-algorithm
- Parameter file: https://github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs

Observed on 2026-11-07; no immutable commit hash captured. Recheck before presenting these as current. The overview describes weights on predicted actions and continuous attention values, author diversity, discovery, and experimentation. Do not read the weights as raw engagement points.

## Numeric snapshot

The parameter source displayed these defaults at inspection. Previous values and the change date below come from the user's account and were not independently verified through a commit diff.

| Signal | User-supplied previous value | Observed default on inspection |
| --- | ---: | ---: |
| Like/favorite prediction | 0.66 | 0.708 |
| Continuous dwell prediction | 0.006 | 0.0075 |
| Share prediction | 2 | 2.118 |
| Post click prediction | 0.3 | 0.274 |
| Video-open prediction | 0.02 | 0 |
| Reply prediction | unchanged | 5 |
| Quote prediction | unchanged | 5 |
| Share via DM prediction | unchanged | 5 |
| Share via copied link prediction | unchanged | 20 |
| Follow-author prediction | unchanged | 4 |

Treat increased emphasis on readable, useful content as an editorial inference. A coefficient increasing from 0.006 to 0.0075 is a 25% parameter change, not evidence of 25% more reach or a fixed reward for each second. Do not assert seconds as the unit without tracing the implementation. A copy-link coefficient of 20 does not make it worth a fixed number of likes or prove it is the dominant contribution for any viewer.

## Preserve these supplied claims as unverified until traced

| Supplied claim | Required verification before repeating as fact |
| --- | --- |
| Click dwell 0.4 to 0.385, not-interested -52.27 to -53.07 | Current parameter definitions, units/transformations, and dated diff |
| New posts receive a first-two-hours/first-200-views boost; accounts under 50K can reach around position 16; early likes select posts | Exact eligibility and scorer implementation, including whether limits are inclusive and the view source |
| First and 32nd likes open discovery routes | Retrieval implementation and relevant conditions; do not infer guaranteed reach |
| Second post receives a 62% factor | Diversity scorer and position-dependent formula; do not turn into a universal posting gap |
| Replies/reposts do not reach strangers; posts older than 48 hours disappear | Relevant discovery filters and feed surface; do not generalize across search, profiles, notifications, or all X |
| Bookmarks are worth zero; hashtags do nothing | Distinguish an absent explicit ranking term from indirect usefulness, retrieval, and product features |
| Video lists require over 10 seconds; hidden-content checks at 64/512 likes | Current list eligibility and moderation path; do not generalize from a single signal or invent a creator tactic |
| Reply AI checks target accounts above 250K; labels last 14–30 days; exceptions apply; notifications are withheld | Detection, labeling, visibility, and notification rules together; verify conditions and deployment evidence |
| One label blocks all non-follower discovery; insult/quality/misinformation labels prevent interaction | Exact label-specific treatment and viewer conditions; avoid blanket shadowban claims |
| Adult media in three of five posts labels the account; pinned low-rated links cause seven-day labels | Aggregation window, label rules, exceptions, and enforcement configuration |
| Copypasta, spam links plus stranger mentions, reply piling, engagement bait trigger penalties | Exact rule and scope before naming a guaranteed penalty; use ordinary quality guidance meanwhile |
| Mutual replies are worth 20, so follow regulars back | Inspect base and additional predicted-reply terms; never recommend artificial reciprocal engagement |
| Like weight highest ever; first change in three weeks; October trend | Repository history covering the claimed interval, not just the latest file |

## Refresh procedure

1. Start with the official repository and its current source tree; verify that it remains the active publication.
2. Locate the relevant parameter, consuming scorer/filter, and tests or configuration. Trace enabled gates and exceptions.
3. Inspect history and capture a commit permalink when claiming a dated change. Separate publication time from demonstrated rollout time.
4. Report what the code establishes and what it does not. If a model output is named but no coefficient or unit is current, leave the value unknown.
5. Update this ledger only when the user requests a skill update. For a one-off answer, give fresh findings without silently rewriting the installed skill.
