# AI sector reference

Companion to `SKILL.md`. Read before research.

**Maintenance note.** Entity lists, model names, and pricing move fast. Treat every
list here as a working checklist. Re-check core model
pricing and availability on every run. Update this file when a lab, benchmark, or
regulation materially changes the landscape.

Last reviewed: 2026-08-15 against live sources.

## 1. Coverage boundaries

**In scope.** Frontier and open-weight model labs. Cloud and compute providers. AI
chips and their supply chain. Datacenters and the power that feeds them. Capital
flowing into all of the above. The application layer built on models. Policy,
regulation, litigation, and safety evaluation.

**In scope only when it changes AI economics.** Consumer devices, enterprise software
incumbents, telecom, semiconductors outside AI accelerators, energy generally.

**Out of scope.** General software news. Crypto. Robotics hardware, unless a foundation
model is the story. Academic results with no path to deployment.

### Layers of the stack

Use these consistently. Most events start in one layer and propagate.

1. **Chips and supply**: accelerators, memory, foundry, networking
2. **Compute and cloud**: hyperscalers, neoclouds, sovereign compute
3. **Power and datacenters**: sites, contracts, grid interconnection
4. **Model labs**: frontier closed labs, open-weight labs
5. **Application layer**: coding, search, agents, vertical AI
6. **Enterprise adoption**: buyers, displacement of incumbents
7. **Policy and safety**: regulators, courts, standards, evaluators
8. **Capital**: venture, secondaries, public markets

## 2. Entities

### Core, check directly every run

| Entity | What it is |
|---|---|
| OpenAI | Frontier lab, GPT models, ChatGPT. Private. |
| Anthropic | Frontier lab, Claude models. Private. |
| Google DeepMind | Frontier lab inside Alphabet, Gemini models. |
| Meta AI | Frontier lab, Llama open-weight models. |
| xAI | Frontier lab, Grok models. Private. |
| DeepSeek | Chinese lab, strong open-weight reasoning models. |
| Alibaba Qwen | Chinese lab, widely used open-weight family. |
| Mistral | European lab, open and closed models. |
| NVIDIA | Dominant AI accelerator maker. Public. |
| Microsoft | Azure cloud, OpenAI partner. Capex and backlog are proxies. |
| Alphabet | Google Cloud, TPUs, DeepMind. |
| Amazon | AWS, Trainium chips, Anthropic investor. |
| TSMC | Manufactures nearly all leading AI chips. |
| Broadcom | Custom accelerator design for hyperscalers. |
| CoreWeave | Largest of the GPU-focused neoclouds. |
| Hugging Face | Open-weight distribution and the de facto model registry. |

### Secondary, scan via triggers

Labs and models: Moonshot AI, Z.ai, MiniMax, Baidu ERNIE, ByteDance Seed, Tencent
Hunyuan, Cohere, AI21, Reka, Safe Superintelligence, Thinking Machines Lab, Liquid AI,
Allen Institute for AI.

Chips and hardware: AMD, Intel, SK Hynix, Micron, Samsung, Cerebras, Groq, SambaNova,
Marvell, Astera Labs, Arista, Credo.

Compute and cloud: Oracle OCI, Nebius, Lambda Labs, Crusoe, Together AI, Fireworks,
Baseten, Modal, IBM, sovereign compute programs.

Power and datacenters: Equinix, Digital Realty, Vertiv, Eaton, GE Vernova, Siemens
Energy, Constellation Energy, Vistra, NextEra, Talen, Bloom Energy.

Application layer: Anysphere (Cursor), Perplexity, Harvey, Sierra, Glean, Abridge,
OpenEvidence, Replit, Vercel, Lovable, Decagon, Clay, ElevenLabs, Synthesia, Suno,
Runway, Black Forest Labs, Midjourney.

Enterprise incumbents exposed to AI: Salesforce, ServiceNow, SAP, Workday, Adobe,
Snowflake, Databricks, MongoDB, Palantir, Atlassian, Intuit, Chegg, Stack Overflow.

Evaluation and safety: METR, Apollo Research, UK AI Security Institute, US CAISI,
Epoch AI, LMArena, Artificial Analysis, SWE-bench maintainers, ARC Prize.

### Long tail

Discovered through papers, funding rounds, regulator dockets, supply chain filings,
job postings, and open-weight derivative ecosystems.

## 3. KPIs and definitions

Define every metric before using it. Ambiguity here is the most common failure.

### Model and product

| Metric | Definition and trap |
|---|---|
| Price per million tokens | State input and output separately. Cached and batch pricing differ, often by 10x. Always date it. |
| Context window | Advertised maximum input length. Measured performance at that length is usually much worse and rarely tested. |
| Total parameters | Model size. For mixture-of-experts models, state active parameters too. |
| Active parameters | What actually runs per token. Drives inference cost far more than total. |
| Tokens served | Volume proxy. Rarely disclosed. Treat leaked figures as estimates. |
| Latency | Time to first token and tokens per second are different. State which. |
| Knowledge cutoff | Training data end date. Needed to assess benchmark contamination. |
| Deprecation date | When a model is withdrawn. Material for anyone building on it. |

### Business

| Metric | Definition and trap |
|---|---|
| Annualized run rate | One month's revenue times twelve. Name the month and label the result as a projection. Usually unaudited. |
| Paying customers | Distinguish from registered, monthly active, and weekly active users. |
| Gross margin | For AI products, inference cost dominates. Often undisclosed or negative early. |
| Backlog or RPO | Contracted future revenue. Hyperscaler RPO is the best public proxy for AI demand. |
| Capex | State guidance versus actual, and the period. Multi-year totals are often reported as annual. |
| Valuation | Value from a priced round, tender offer, or secondary sale. Name the transaction type and lead. |

### Compute and power

| Metric | Definition and trap |
|---|---|
| Chip count | State the specific chip. Generations differ several-fold in performance. |
| GPU-hours | Usable for training run size. Needs the chip type to mean anything. |
| FLOPs | Total compute for a training run. State precision, since numbers differ by format. |
| Megawatts or gigawatts | Datacenter capacity. Distinguish contracted, under construction, and energized. |
| PUE | Power usage effectiveness, a datacenter efficiency ratio. Lower is better. |

## 4. Regulators and public records

| Body | Jurisdiction | What to check |
|---|---|---|
| EU AI Office | EU | AI Act implementation, general-purpose model obligations, codes of practice |
| US BIS | US | Export controls on advanced chips and manufacturing equipment |
| FTC | US | Competition and consumer protection actions involving AI |
| State legislatures | US | California, Colorado, Texas, New York AI statutes and effective dates |
| NIST and CAISI | US | Standards, evaluation frameworks |
| UK AISI | UK | Pre-deployment safety evaluations |
| CAC | China | Generative AI filings and approvals |
| Courts | US | Training data copyright, trade secrets, product liability |
| ISO/IEC | Global | 42001 AI management systems and related standards |

Live litigation worth tracking: publisher and author suits against model developers,
music label suits against audio generators, studio suits against image and video
generators, and any ruling touching fair use for training. Check dockets directly rather
than relying on coverage.

## 5. Strong sources

**Artifacts**: model cards and system cards, API documentation, pricing pages,
changelogs, model weights on Hugging Face, GitHub repositories, arXiv papers.

**Independent evaluation**: LMArena, Artificial Analysis, SWE-bench leaderboards, ARC
Prize, METR task suites, Epoch AI datasets, safety institute reports.

**Filings and financials**: 10-K and 10-Q for public companies, hyperscaler earnings
calls for capex and backlog, NVIDIA earnings for demand signal, TSMC monthly revenue.

**Reporting**: The Information, Bloomberg, Reuters, Financial Times, Wall Street
Journal, SemiAnalysis, Stratechery, Import AI.

**Discovery only**: lab blog posts, X and LinkedIn announcements, demo videos,
newsletters, Reddit and Hacker News threads, benchmark screenshots.

Chinese-language sources matter for Chinese labs, where English coverage lags by days
and often misses the technical report entirely.

## 6. Materiality triggers

### Critical or high

- Frontier model release that moves the capability frontier
- Price change per token of 30% or more, in either direction
- Export control change, or chip supply materially reallocated
- A lab gaining or losing a major compute partner
- Court ruling on training data or fair use
- Safety incident causing real-world harm, or a serious misuse disclosure
- Funding round or tender that resets a major private valuation
- License change on widely used open weights
- Regulation taking legal effect, as distinct from being proposed
- Hyperscaler capex guidance revised materially
- A benchmark result independently verified that vendors had disputed

### Medium

- New model in an existing family with clear measured improvement
- Named enterprise win displacing an incumbent
- Research lead or safety lead joining or leaving a frontier lab
- Datacenter or power deal above roughly one gigawatt
- Deprecation of a widely used model

### Low, usually skip

- Demos, teasers, and waitlists
- Benchmark increments inside noise, or on saturated benchmarks
- Partnerships with no disclosed terms
- Rebrands and logo changes
- Funding rumors with no named lead investor
- "We are working on" statements
- Model releases with no public or customer access yet

## 7. Calendar anchors

| When | What |
|---|---|
| Late Jan, Apr, Jul, Oct | Microsoft, Alphabet, Amazon, Meta earnings. Capex and backlog. |
| Feb, May, Aug, Nov | NVIDIA earnings. The clearest public demand signal. |
| Monthly, ~10th | TSMC revenue. Early read on chip demand. |
| March | NVIDIA GTC |
| April or May | ICLR |
| May | Google I/O, Microsoft Build |
| June | CVPR, Apple WWDC |
| July | ICML |
| December | NeurIPS, AWS re:Invent |
| Variable | OpenAI DevDay, Meta Connect, lab release events |

EU AI Act obligations phase in on staggered dates. Keep the current schedule in
`config/watchlist.yaml` and check what takes effect next, since the phase-in is the
single most predictable source of policy news.

## 8. Search terms and aliases

**Lab aliases**: Google DeepMind covers Gemini, Gemma, and prior Brain work. Meta AI
covers FAIR and Llama. Alibaba covers Qwen and Tongyi. Z.ai was formerly Zhipu AI.
ByteDance research appears as Seed or Doubao.

**Useful query patterns**: `"model card" <model name>`; `<lab> pricing site:<domain>`;
`<benchmark> leaderboard <year>`; `<model> independent evaluation`; `<model>
contamination`; `<company> capex guidance <quarter>`; `<lab> compute agreement`;
`site:arxiv.org <topic> <year>`; `<company> v. <lab> complaint docket`.

**Chinese terms**: 大模型 (large model), 开源 (open source), 算力 (compute power),
备案 (regulatory filing), 推理 (inference).

**Time-window discipline**: always include the current year in queries. AI search
results skew heavily toward older, more-linked content.

## 9. Plain-language glossary

Use these glosses, or better ones, on first use in any output. Consistency matters more
than elegance.

| Term | Plain gloss |
|---|---|
| Token | A chunk of text, roughly three quarters of a word. Models are priced per token. |
| Context window | How much text a model can consider at once. |
| Parameters | The adjustable values inside a model. Loosely, its size. |
| Mixture of experts | A design where only part of the model runs for each token, cutting cost. |
| Inference | Running a trained model. The ongoing cost, as opposed to building it. |
| Training run | The one-time process of building a model. It requires substantial compute. |
| Pre-training | Learning from raw data. Post-training is the tuning that follows. |
| Fine-tuning | Adapting an existing model to a narrower task. |
| Distillation | Training a small model to copy a larger one. |
| Quantization | Shrinking a model to run cheaper, usually with some quality loss. |
| Open weights | The model file is downloadable. Its license may still restrict use. |
| Reasoning model | A model that works through steps before answering, trading time for accuracy. |
| Test-time compute | Letting a model think longer to do better. Costs more per answer. |
| Agent | A model that can take actions in software and produce responses. |
| Tool use | A model calling external software, such as search or code execution. |
| RAG | Retrieval that lets a model consult relevant information while answering. |
| Benchmark | A standard test used to compare models. |
| Eval | Any structured test of model behavior, including safety testing. |
| SWE-bench | A test of whether a model can fix real bugs in open source code. |
| Contamination | When test questions appear in training data, inflating scores. |
| pass@1 | Score when the model gets one attempt. pass@k allows k attempts. |
| Hallucination | A confident, fluent, wrong answer. |
| Jailbreak | A prompt that bypasses a model's safety rules. |
| Red-teaming | Deliberately attacking a system to find failures before release. |
| System card | A lab's published document on a model's capabilities and risks. |
| Scaling laws | The observed pattern that more compute and data yield better models. |
| Frontier model | One of the most capable models available at a given time. |
| HBM | High bandwidth memory. The main supply bottleneck for AI chips. |
| Accelerator | A chip built for AI work. GPUs are the common type. |
| Neocloud | A newer cloud company renting GPUs, competing with the hyperscalers. |
| Hyperscaler | Microsoft, Amazon, or Google, at cloud scale. |
| Capex | Money spent on buildings and equipment, here mostly chips and datacenters. |
| RPO | Contracted revenue scheduled for future delivery. A demand indicator. |
| ARR | Annualized run rate. One month multiplied by twelve, usually unaudited. |
| Export controls | Government rules limiting which chips can be sold where. |
