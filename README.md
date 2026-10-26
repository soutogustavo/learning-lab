# Learning Lab

Hands-on notes and minimal runnable examples from studying ML, MLOps and cloud tools — organized by concept, with gotchas and lessons learned.

This is my personal reference: when I remember *"I've done something like this before"*, this is where I look first. Each topic focuses on **one concept per example**, explains the *why* (not just the *how*), and records the pitfalls I ran into along the way.

> **Note:** these are study notes, not production code. Library APIs change over time, so each topic records the date it was studied and the versions used.


## Index

### Foundations

| Topic | What's inside | Status |
|---|---|---|
| [Statistics](./foundations/statistics) | Central tendency, variability, correlation, distributions (binomial), selection bias, A/B testing | ✅ |
| [Metrics](./foundations/metrics) | Confusion matrix, ROC curve, cross-validation | ✅ |
| [Algorithms](./foundations/algorithms) | Data structures and algorithms applied to data science | ✅ |

### Data

| Topic | What's inside | Status |
|---|---|---|
| [Pandas](./data/pandas) | Loading and fixing badly formatted CSV files | ✅ |
| [Visualization](./data/visualization) | Seaborn: legend position, plot size, grids and x-ticks | ✅ |

### Machine Learning

| Topic | What's inside | Status |
|---|---|---|
| [Boosting](./ml/boosting) | XGBoost and LightGBM: training, feature importance, core parameters | ✅ |

### Tooling

| Topic | What's inside | Status |
|---|---|---|
| [Jupyter](./tooling/jupyter) | Sharing variables and data across notebooks | ✅ |

**Status:** ✅ Done · 🟡 In progress · ⚪ Planned



## Roadmap

Topics currently being studied or planned next:

- 🟡 **GenAI / LangChain**: prompts and models, structured output, tools, retrieval
- ⚪ **GenAI / LangGraph**: stateful agents, persistence, human-in-the-loop
- ⚪ **Data / SQL**: analytical SQL for time-series anomaly detection (window functions, spines, z-scores)
- ⚪ **ML / Time series**: forecasting baselines, temporal validation, lag features
- ⚪ **MLOps / Terraform**: AWS infrastructure as code


## How each topic is organized

```
<group>/<topic>/
├── README.md          # when to use it, cheat sheet, gotchas, open questions
├── pyproject.toml     # isolated environment with pinned versions (newer topics)
├── .env.example       # required environment variables, if any (never real keys)
└── NN-concept/        # one concept per folder: small, self-contained examples
```

Each topic `README.md` follows the same structure:

- **Studied / versions**: when it was studied and which library versions were used
- **When to use it / when not to**
- **Cheat sheet**: *"I want to do X"* → which file to open
- **Gotchas**: what broke silently, and why
- **Open questions**: what I still want to understand better


## Running the examples

Newer topics are self-contained environments managed with [uv](https://docs.astral.sh/uv/):

```bash
cd genai/langchain
uv sync
uv run python 01-prompts-and-models/basic_chat.py
```

Topics that need API keys include a `.env.example`. Copy it to `.env` and fill in your own values.

Older notebooks don't have pinned environments yet; the main library versions are noted in each notebook when relevant.


## Related projects

End-to-end, applied work lives in dedicated repositories:

- [**rossmann-forecasting-benchmark**](https://github.com/soutogustavo/rossmann-forecasting-benchmark): multi-store sales forecasting (Prophet baseline → global XGBoost) with a retraining pipeline on AWS

---

## License

[MIT](./LICENSE)