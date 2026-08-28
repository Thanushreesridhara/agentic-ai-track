# Agentic AI Track — Foundations

My work from Week 1 (Foundations) of the Agentic AI Engineering course.

## AI Digital Twin (`twin/`)

A conversational agent that answers questions about my career and background,
built on the OpenAI API with a hand-written tool-calling agent loop (no framework)
and served through a Gradio web UI.

- `app.py` — Gradio chat interface + agent loop (`while finish_reason == "tool_calls"`)
- `context.py` — builds the system prompt from a LinkedIn/CV PDF (`pypdf`) plus `summary.txt`, with guardrails
- `tools.py` — function-calling tools: record a visitor's email (lead capture) and log unanswered questions, with Pushover push notifications
- `styles.py` — custom Gradio CSS/JS theme (light/dark)
- `RENDER_INSTRUCTIONS.md` — deploying the twin to Render

Run locally:

```bash
cd twin
pip install -r requirements.txt
# create .env with OPENAI_API_KEY, PUSHOVER_USER, PUSHOVER_TOKEN
python app.py
```

## Labs

- `1_lab1.ipynb` — first LLM API calls; OpenAI and local Ollama models; chained calls
- `2_lab2.ipynb` — calling many providers through OpenAI-compatible endpoints; LLM-as-a-judge to rank responses
- `3_lab3.ipynb` — building the tool-calling agent loop from scratch
- `4_lab4.ipynb`, `5_extra.ipynb` — course material
