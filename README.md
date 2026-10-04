# Singlepost Agent

Automated Norwegian corporate intelligence and web research agent built for the Signalpost/Builderr challenge.

## Data Sources & APIs
- **Brønnøysundregistrene (BRREG):** Official Norwegian business registry API.
- **Exa AI:** Neural web search engine for company website discovery and fallback domain resolution.
- **OpenAI (`gpt-4o-mini`):** LLM-powered structured fact extraction for social profiles, key leadership, and operational details.

## How to Runs
```bash
source .venv/bin/activate
export EXA_API_KEY="your-exa-key"
export OPENAI_API_KEY="your-openai-key"

python3 -m scripts.run_competition_batch \
  --organisations tests/fixtures/batch-orgs-1.txt \
  --bulk data/sample_bulk.csv.gz \
  --output output.json \
  --profiles-output profiles.jsonl \
  --report report.json \
  --run-id submission-run