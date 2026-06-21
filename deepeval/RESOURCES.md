# Resources

## Official Documentation

- **[DeepEval Docs](https://docs.confident-ai.com/)** - Official documentation from Confident AI
  - Comprehensive guide to all metrics, features, and integrations
  - Start here for authoritative information
  
- **[DeepEval GitHub](https://github.com/confident-ai/deepeval)** - Open-source repository
  - 16.3k stars, actively maintained
  - Example code and community discussions
  - Issues and feature requests

## Key Concepts to Understand

### Evaluation Frameworks
- **[LLM Evaluation Overview](https://docs.confident-ai.com/docs/getting-started)** - Understanding systematic evaluation vs intuitive assessment
- **[Metrics Introduction](https://docs.confident-ai.com/docs/metrics-introduction)** - How DeepEval's metrics work

### RAG-Specific Resources
- **[RAG Metrics Guide](https://docs.confident-ai.com/docs/metrics-answer-relevancy)** - Answer relevancy, faithfulness, contextual precision/recall
  - Critical for your container shipping use case
  - Focus on: faithfulness (no hallucinations), contextual recall (retrieving right docs), answer relevancy

### Operational Data Evaluation
- **[Hallucination Detection](https://docs.confident-ai.com/docs/metrics-hallucination)** - Detecting fabricated information
  - High priority: fabricated ship names, routes, or metrics would be catastrophic
- **[Factual Accuracy](https://docs.confident-ai.com/docs/metrics-faithfulness)** - Ensuring outputs are grounded in retrieved context

## Community Resources

- **[DeepEval Discord](https://discord.gg/3SEyvpgu2f)** - Active community for questions and discussions
- **[DeepEval Reddit](https://www.reddit.com/r/deepeval/)** - Community discussions and use cases

## Alternatives (for context)
- **Ragas** - Another RAG evaluation framework (mentioned for comparison, not deep dive)
- **LangSmith** - LangChain's evaluation platform
- **Confident AI Platform** - Cloud platform that integrates with DeepEval for team collaboration

## To Explore Later
- Advanced custom metrics creation
- Production monitoring and CI/CD integration
- Statistical evaluation methods beyond LLM-as-judge
