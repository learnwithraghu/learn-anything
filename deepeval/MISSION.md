# Mission: Learning DeepEval

## Why

I am managing a team building a RAG system. Currently, our evaluation approach is intuitive ("does this output look good?") rather than systematic. I need to understand DeepEval's capabilities, features, and tradeoffs well enough to:

- Guide the team's evaluation strategy
- Make architectural decisions about metrics and approaches
- Review their work and spot gaps
- Unblock the team when they hit evaluation challenges

This is a **strategic oversight role** — I need depth of understanding without hands-on implementation.

## Success Looks Like

After completing this learning journey, I can:

1. **Review the team's evaluation approach** and identify missing metrics or weak spots
2. **Suggest concrete improvements** to evaluation strategy based on our RAG use case
3. **Make informed tradeoffs** between different evaluation approaches (speed vs accuracy, cost vs coverage, etc.)
4. **Explain to stakeholders** why we chose certain metrics and what the results mean
5. **Recognize when evaluation scores are misleading** and guide the team to better metrics

Importantly: I can do all of this **without needing to write the code myself**.

## Constraints

**Time commitment**: 1-2 hours per week, spread across short sessions (15-30 minutes each)

**Learning style**: 
- Heavy emphasis on **decision frameworks** and **conceptual models**
- Code examples to illustrate concepts (I'll read them, not write them)
- Real-world scenarios and tradeoffs
- Visual diagrams for architecture and flow

**Current knowledge**:
- I understand RAG architecture and the business problem
- Evaluation has been mostly intuitive, not systematic
- I need to level up from basic metrics to sophisticated evaluation

**Team context**:
- Team is early in evaluation or using only basic metrics
- Building a RAG system for **container shipping operational data**
  - Daily PDF reports from ships (routes, schedules, metrics)
  - Processed into VectorDB, LLM generates answers
  - Quick search UI for operational queries
- Need to increase sophistication of evaluation approach

**Domain-specific risks**:
- Factual accuracy is critical (wrong metrics = wrong business decisions)
- Numerical precision matters (cargo counts, fuel consumption must be exact)
- High hallucination risk with structured data
- Temporal queries are common ("yesterday", "last week")

## Out of Scope

These topics are explicitly excluded (at least initially):

- **Writing custom DeepEval metrics from scratch** — understanding built-in metrics is sufficient
- **Deep comparative analysis of all evaluation frameworks** — mention alternatives for context, but focus on DeepEval
- **Advanced statistical methods for evaluation** — practical decision-making over academic rigor
- **LLM fine-tuning and model improvement** — we're evaluating outputs, not training models

We stay focused on: understanding DeepEval's capabilities, choosing appropriate metrics, interpreting results, and making strategic decisions.
