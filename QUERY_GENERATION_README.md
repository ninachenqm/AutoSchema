# AutoSchema — Polymer Query Generation

**Repository:** https://github.com/ninachenqm/AutoSchema

**Branch:** `task1-queries`

## 1. Setup

From the repository root:

```bash
pip install -r requirements.txt
```

Configure the LLM API credentials using `.env.example` as a reference.

Place the seed PDFs in:

```text
data/seeds_disulfide/    # 3 PDFs
data/seeds_batteries/    # 3 PDFs
data/seeds_glass_transition/    # 3 PDFs
```

## 2. Generate Queries

**Disulfide-containing polymers**

```bash
python prompt_pipeline.py --domain polymer --last_tier disulfide --seeds data/seeds_disulfide --output runs/polymer/disulfide/run_01
```

**Polymers for battery applications**

```bash
python prompt_pipeline.py --domain polymer --last_tier batteries --seeds data/seeds_batteries --output runs/polymer/batteries/run_01
```

**Glass transition in polymers**

```bash
python prompt_pipeline.py --domain polymer --last_tier glass_transition --seeds data/seeds_glass_transition --output runs/polymer/glass_transition/run_01
```

## 3. Outputs

Each run creates the following files in its specified output directory:

- `queries.json` — Up to 8 generated queries.
- `papers.jsonl` — Structured information extracted from the seed PDFs.
- `seeds/` — Copies of the input PDFs.

**Note:** Use a new output directory for each run to avoid overwriting previous results. Seed PDFs are stored locally and shared separately, not committed to GitHub.