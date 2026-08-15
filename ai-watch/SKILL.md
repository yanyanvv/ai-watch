---
name: ai-watch
description: Create current AI industry briefs, alerts, model release reviews, company monitors, capability checks, source searches, comparisons, and deep dives. Use when a user asks what changed in AI or wants research on model labs, chips, compute, funding, pricing, applications, regulation, litigation, or safety. Use primary sources and independent evaluations, separate company claims from verified results, rank material changes, explain business effects in plain English, save reusable research state when possible, and produce a concise Markdown brief with a polished one-page PDF.
---

# AI Watch

Find material changes in AI and explain them in plain English. Use current evidence, combine repeated coverage, and keep claims close to their sources.

## Default run

When the user asks to run the skill without more detail, create a weekly brief with these defaults:

- Period: the previous seven complete days through the research cutoff
- Scope: model labs, compute and chips, capital, policy, and applications
- Geography: global, with extra attention to the United States and China
- Audience: an intelligent reader with no AI background
- Items: four or five ranked developments
- Length: 600 to 750 words
- Delivery: full Markdown in the conversation and a polished one-page PDF
- State: a provisional baseline when durable storage is available

State the period, cutoff, timezone, and scope in one short header line. Ask a question only when a missing choice would materially change the work.

## Modes

Infer the mode from the request.

- **brief**: Review the most important changes during a period. This is the default.
- **alert**: Report watchlist triggers from the last 24 to 72 hours.
- **source-search**: Find the strongest sources for one question.
- **lab**: Review one lab or company.
- **model-release**: Assess capability, evidence, price, access, and limits.
- **capability-track**: Follow one capability or benchmark over time.
- **compute-and-capital**: Review chips, datacenters, power, funding, and valuations.
- **policy**: Review regulation, export controls, litigation, and standards.
- **comparison**: Compare models, labs, products, or business models.
- **deep-dive**: Answer one focused question thoroughly.
- **landscape**: Map a market layer or competitor group.
- **setup**: Define coverage, sources, metrics, watchlists, and cadence.

## Workflow

### 1. Set the coverage contract

Record the mode, period, cutoff, timezone, geography, languages, audience, scope, exclusions, sources available, and material access limits.

For recurring work, divide coverage into three groups:

- **Core**: Check about 15 to 20 entities directly on every run.
- **Secondary**: Scan about 25 to 40 entities through triggers, release notes, earnings calendars, and material news searches.
- **Long tail**: Discover entities through themes, papers, regulators, funding, supply chains, and early signals.

Claim entity-level coverage only when the run record shows the entities and source types checked.

### 2. Read the sector reference

Read `references/ai-industry.md` before research. Verify all time-sensitive facts, entity lists, prices, release status, and policy dates.

### 3. Build the research plan

Check the angles that matter for the request:

- Model releases, version changes, deprecations, prices, limits, and availability
- Independent evaluations, replications, leaderboards, and red-team results
- Technical reports, model cards, system cards, weights, and code
- Chip supply, datacenters, power contracts, capex, and cloud demand
- Funding, tender offers, secondary marks, revenue, and customer evidence
- Enterprise adoption, named wins, usage, and incumbent displacement
- Regulation, export controls, court rulings, standards, and enforcement
- Research and safety leadership changes
- Open-weight licenses and derivative ecosystems
- Evidence that weakens the leading interpretation
- Chinese-language sources when they may change the conclusion

Record source families, search angles, access failures, no-hit results, and the cutoff. A no-hit result means the checked sources contained no material item.

### 4. Use strong sources

Match the source to the claim. Use this order:

1. Court records, regulator decisions, laws, filings, standards, patents, and government data
2. Checkable artifacts such as model weights, public API behavior, pricing pages, documentation, code, technical reports, and reproducible papers
3. Independent evaluations, academic replications, safety institute results, and private test sets
4. Lab announcements, company blogs, earnings calls, and executive interviews
5. Authorized private evidence and user-provided documents
6. Newsletters, social posts, demos, forums, anonymous claims, aggregators, and search snippets

Use discovery sources to find leads. Confirm material claims with stronger evidence. Treat reposts and articles based on the same announcement as one source.

For a market-moving claim, seek a source of record or checkable artifact plus independent support. Mark the event as single-source in saved state when that support does not exist.

Never imply access to subscriptions, connectors, databases, or saved state that the environment does not provide. Respect access controls.

### 5. Consolidate events

Create one record for each underlying event. Attach later reports and corrections to that record.

Store:

- Event ID, headline, type, entities, themes, layer, and geography
- Event, announcement, publication, availability, first-seen, and update dates
- Status: `new`, `meaningful_update`, `recycled`, `correction`, `contradicted`, or `superseded`
- Atomic claims and evidence labels
- Metrics with values, units, currency, definitions, periods, and methods
- Original source, independent support, derivative coverage, and conflicts
- Materiality, confidence, implications, and next indicators

Use these labels in saved state:

- **FACT**: Direct support from the cited evidence
- **VENDOR CLAIM**: A claim from the party that benefits
- **INDEPENDENTLY VERIFIED**: Outside reproduction or measurement
- **REPORTED**: Credible reporting without direct confirmation
- **ESTIMATE**: A calculation or forecast from stated inputs
- **INFERENCE**: An interpretation based on cited facts
- **SCENARIO**: A conditional future outcome
- **RUMOR**: A material claim without enough confirmation
- **WATCH SIGNAL**: Early evidence that needs follow-up

Express these distinctions in normal sentences in reader-facing work. Keep the labels in state.

### 6. Check capability claims

Treat a lab's benchmark result as a vendor claim until an outside evaluator reproduces it.

Record these conditions before comparing scores:

- Benchmark name, version, and test date
- Evaluation harness
- Prompting method
- Sampling method, including pass@1, pass@k, best-of-n, or voting
- Reasoning budget
- Tools, retrieval, code execution, and internet access
- Public, held-out, or private test set
- Model training cutoff and contamination risk

Compare scores only when the conditions match. Explain any mismatch.

Check for saturated benchmarks, omitted standard tests, curated demos, waitlists, price, rate limits, latency, context limits, regional access, and terms. Separate tested capability from practical availability.

State when independent testing does not exist.

### 7. Rank material change

Assess materiality and confidence separately.

Materiality considers relevance, capability, cost, access, capital, compute, market share, regulation, breadth, duration, urgency, novelty, and affected entities.

Confidence considers source authority, directness, measurement conditions, independent support, conflicts, and full-source access.

Use `critical`, `high`, `medium`, or `low` for materiality. Use `high`, `medium`, or `low` for confidence. Use numeric scores only when the user asks for them.

High-priority examples include:

- A frontier model that changes practical capability
- A large price change
- A major compute, chip, power, funding, or customer commitment
- A court ruling or regulation taking effect
- A serious safety incident
- A widely used open-weight license change

Usually skip demos without artifacts, small benchmark changes, undisclosed partnerships, rebrands, minor hiring, funding rumors, and unavailable products.

### 8. Explain each selected event

Determine what changed, what was known, why the update matters, who is affected, how strong the evidence is, what evidence limits the conclusion, and what resolves next.

Keep the full analysis in saved state. Put only the useful conclusion, support, and caveat in the brief.

Call a pattern a trend after enough evidence accumulates. A useful default is three distinct events across two source families and two dates. One authoritative disclosure may settle the question sooner.

## Saved state

When durable storage is available, use this structure:

```text
briefs/ai/
  config/
    coverage.yaml
    sources.yaml
    watchlist.yaml
    metrics.yaml
  state/
    events.jsonl
    claims.jsonl
    documents.jsonl
    metrics.jsonl
    models.jsonl
    benchmarks.jsonl
    themes.md
    entities.yaml
  runs/
    YYYY-MM-DD.json
  reports/
    YYYY-MM-DD.md
output/pdf/
  ai-watch-YYYY-MM-DD.pdf
```

Keep dated reports unchanged. Add corrections to canonical state and the next report. Preserve user edits. Recheck core pricing and availability on every run.

When storage is unavailable, end recurring work with a short continuity note covering the cutoff, active themes, open triggers, corrections, and next catalysts.

## Weekly brief format

Use this order:

```text
# AI this week: <plain headline>
One line with period, cutoff, and scope.

## The one thing to know
One or two short sentences.

### Background
Only when essential. Keep it under 50 words.

## What changed
Four or five ranked items.

## What to watch next
Ordered by resolution date.

## What I checked
One or two short lines.
```

Each ranked item needs a plain headline, three or four short sentences, a clear effect, an evidence limit when material, and nearby source links.

Keep useful numbers beside the claims they explain. Omit standalone sections for numbers, risks, counterarguments, and proof.

## What to watch next

- Sort entries by resolution date.
- Lead with events that may resolve before the next run.
- Put at least half the entries inside the next four weeks.
- Include later dates only when they force a current decision.
- Use scheduled, checkable events such as earnings, hearings, deadlines, and release dates.
- State what the event could change.
- Omit undated entries from the dated list.
- Check the sector reference calendar before writing.

## One-page PDF

When files can be created, save `output/pdf/ai-watch-YYYY-MM-DD.pdf`.

- Use the same facts and conclusions as the Markdown brief.
- Keep all ranked items and the near-term watch list.
- Shorten supporting detail to fit one page.
- Use a clear title, date, hierarchy, high contrast, and generous spacing.
- Keep body text at 9.5 points or larger.
- Make source links readable and clickable.
- Render the PDF to an image and inspect it.
- Fix clipping, crowding, broken links, stray glyphs, weak contrast, and uneven spacing.

Show the full brief in the conversation. Treat Markdown as the canonical report.

## Other output modes

- **Model release**: Explain the product, new capability, measurement source, price, access, limits, and affected users.
- **Capability track**: Show comparable scores and measurement conditions over time.
- **Compute and capital**: Distinguish planned, contracted, installed, and spent amounts.
- **Policy**: State the jurisdiction and whether a measure is proposed, adopted, or in force.
- **Source search**: Return a focused answer and a short source table.
- **Alert**: Return only triggered changes. Include the cutoff when no trigger fired.
- **Comparison**: Use consistent dimensions and periods. Keep tables under six columns.
- **Deep dive**: Add chronology, incentives, economics, competing evidence, and observable signposts.

## Writing rules

- Start with the answer.
- Write for an intelligent reader with no AI background.
- Use one idea per sentence. Aim for 8 to 16 words.
- Break sentences longer than 20 words when clarity improves.
- Use common words, short verbs, and active voice.
- Identify each company and technical term on first use.
- Explain a benchmark before giving its score.
- Keep paragraphs to two sentences when possible.
- Put analysis beside its evidence.
- State conclusions directly.
- Use commas, periods, or colons in place of em dashes.
- Avoid formulaic contrast sentences.
- Remove slogans, hype, filler, empty transitions, repeated conclusions, and generic market commentary.
- Use each fact and number once unless a comparison needs repetition.
- End with the required output. Omit routine follow-up questions.

## Final checks

Confirm all of the following:

- The result answers the request and uses current evidence through the cutoff.
- Repeated reporting is combined into one event.
- Event, announcement, publication, and availability dates are clear.
- Every material fact has support.
- Every number has a period, unit, currency, definition, and source.
- Benchmark comparisons use matching conditions.
- Vendor claims and outside results remain distinct.
- Capability and availability remain distinct.
- Materiality and confidence remain separate.
- Relevant caveats appear beside the claims they qualify.
- At least half the watch list resolves within four weeks, or the list is shorter.
- The report contains 600 to 750 words.
- The prose contains no unexplained acronyms, hype, em dashes, slogans, filler, or repeated conclusions.
- The Markdown report and one-page PDF exist when files can be created.
- The PDF has been rendered and visually checked.

## Reference

Read `references/ai-industry.md` before research. It contains coverage boundaries, entity groups, metric definitions, public records, source guidance, materiality triggers, calendar anchors, search terms, and plain-language definitions.
