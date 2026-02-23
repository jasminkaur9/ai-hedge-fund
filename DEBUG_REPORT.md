# AI-Hedge-Fund Debug Report

**Author:** Jasmin Kaur
**Date:** 2026-02-23
**Tool:** Claude Code (Opus 4.6)

---

## Setup

- Cloned `virattt/ai-hedge-fund` (45K+ stars)
- Installed Poetry and project dependencies
- Configured `.env` with OpenAI API key
- Ran CLI: `poetry run python src/main.py --tickers AAPL,MSFT,NVDA --analysts-all --model gpt-4.1 --start-date 2024-01-01 --end-date 2024-03-01`

## Bug Found: `UnboundLocalError` in News Sentiment Agent

### Symptom
All 17 analyst agents ran successfully in parallel, but the system crashed during the News Sentiment agent's execution:

```
UnboundLocalError: cannot access local variable 'sentiments_classified_by_llm'
where it is not associated with a value
```

### Root Cause
In `src/agents/news_sentiment.py`, the variable `sentiments_classified_by_llm` was initialized **inside** a nested conditional block (line 64, inside `if articles_without_sentiment:`), but referenced **outside** that block (line 132, in the reasoning dictionary).

When `company_news` was empty or all articles already had sentiment data, the code skipped the initialization but still tried to use the variable, causing the crash.

### Fix Applied
Moved the initialization of `sentiments_classified_by_llm = 0` to **before** the `if company_news:` block (line 57), so it's always defined regardless of which code path executes.

**File:** `src/agents/news_sentiment.py`
**Lines changed:** 57 (added init), 64 (removed duplicate init)

### Verification
Re-ran the system after the fix. The News Sentiment agent completed successfully, returning:
```json
{
  "AAPL": {
    "signal": "neutral",
    "confidence": 0.0,
    "metrics": {
      "articles_classified_by_llm": 0
    }
  }
}
```

## Additional Observation: API Quota Limit (Not a Code Bug)

During testing, the Warren Buffett agent returned "Insufficient data" due to an OpenAI 429 error (quota exceeded). This is an API billing issue, not a code bug. The error handling in `src/utils/llm.py` gracefully retries 3 times before falling back, which is correct behavior.

## Other Notes

- **Python 3.14 compatibility warning:** `langchain_core` emits a `Pydantic V1 not compatible with Python 3.14` warning. The project specifies `python = "^3.11"` — this is a known upstream issue with LangChain, not an ai-hedge-fund bug.
- **Interactive prompts:** The CLI uses `questionary` for interactive model/analyst selection, which fails in non-TTY environments. The `--analysts-all` and `--model <name>` flags bypass this correctly.
