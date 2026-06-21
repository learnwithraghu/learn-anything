# Notes

## User Preferences

- Manager role — strategic oversight, not hands-on coding
- Prefers decision frameworks and conceptual models
- Wants code examples to illustrate, but won't write code
- Short sessions (15-30 minutes)
- 1-2 hours total per week
- **SVG Quality is critical** — wants visuals with Anthropic technical blog quality (no overlapping text, proper spacing, clean rendering)

## Domain Context

**RAG Use Case**: Container shipping operational data search

**Data Pipeline**:
- Daily PDF reports from ships
- Contains: route schedules, daily operations, key metrics
- Processed into VectorDB
- LLM generates answers from retrieved context

**Search Interface**: Quick search UI for operational queries

**Critical Evaluation Concerns**:
- Factual accuracy (wrong metrics = wrong decisions)
- Numerical precision (cargo counts, fuel consumption must be exact)
- Temporal relevance ("yesterday" vs "last week")
- Structured data extraction quality (PDF tables → vector embeddings)
- High hallucination risk (fabricated ship names, routes, metrics)

**Example Queries**:
- "How many containers did Ship Atlas deliver yesterday?"
- "What was fuel consumption on Singapore-Rotterdam route last week?"
- "Which ships are behind schedule?"

## Teaching Strategy

Focus on evaluation metrics most relevant to operational data:
- Answer relevance (did we answer the right question?)
- Faithfulness (is the answer grounded in retrieved docs?)
- Contextual recall (did we retrieve the right documents?)
- Contextual precision (did we retrieve irrelevant documents?)
- Numerical/factual accuracy
- Hallucination detection
