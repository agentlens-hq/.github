# When your AI agent breaks, AgentLens tells you exactly which decision caused it — and what to change.

AgentLens captures every LLM call, tool call, and error your agent makes, then analyzes the trace and tells you the root cause in plain English. Not logs you have to dig through — the answer. It runs entirely on your machine: no dashboard, no signup, no data leaves your laptop.

```
$ agentlens diagnose 070901b0

ROOT CAUSE:   tool_selection
FAILED AT:    Step 2 (search_web)
WHY:          Both tools had near-identical descriptions — the agent
              treated them as interchangeable and picked the wrong one.
FIX:          Rewrite tool descriptions so search_web is clearly for
              external lookup and query_db is clearly for local records.
CONFIDENCE:   0.90
```

It catches six failure categories automatically — `tool_selection` · `loop` · `cascade` · `context_pollution` · `state_drift` · `overflow` — plus hallucinated tool parameters, and works offline with no API key.

## Install

```bash
pip install runlens
```

Two lines to integrate:

```python
import agentlens
agentlens.init()   # patches Anthropic + OpenAI automatically
```

## Links

- **Try it without installing:** [agentlens.run/demo.html](https://agentlens.run/demo.html) — interactive diagnosis of a real broken agent
- **Website:** [agentlens.run](https://agentlens.run)
- **Code:** [agentlens-hq/agentlens](https://github.com/agentlens-hq/agentlens)

## Works with

Anthropic · OpenAI · LangGraph · CrewAI · AutoGen · PydanticAI · raw API
