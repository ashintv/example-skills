# LLM Security Rules & Threat Mitigations

1. **Least Privilege System Persona**: System prompts should grant the agent only the minimum context and permissions required to perform its designated task.
2. **Context Window Partitioning**: Keep sensitive internal business logic isolated from external user chat history.
3. **Dual LLM Verification Pattern**: For high-risk financial or database mutation workflows, pipe the proposed tool parameters through an independent secondary LLM judge model to detect prompt injections before execution.
