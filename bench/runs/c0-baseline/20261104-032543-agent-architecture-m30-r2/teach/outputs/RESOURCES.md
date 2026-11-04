# Agent architecture Resources

## Knowledge

- [Article: "Effective context engineering for AI agents" (Anthropic Engineering)](https://anthropic.com/engineering/effective-context-engineering-for-ai-agents)
  The best single source on the context window as a finite budget, context rot, just-in-time retrieval, compaction, structured note-taking and sub-agents. Use for: anything about what to keep in context and what to keep outside it.
- [Docs: "Context windows" (Claude Platform Docs)](https://platform.claude.com/docs/en/build-with-claude/context-windows)
  Official description of how turns, tool results and tool definitions accumulate in the window, how thinking counts, compaction, and what happens on overflow. Use for: what exactly counts toward the window and why each call carries the whole history.
- [Docs: "Memory" concepts (LangChain / LangGraph)](https://docs.langchain.com/oss/python/concepts/memory)
  Short-term (per conversation) versus long-term (across conversations) memory, semantic, episodic and procedural memory, and writing memories on the hot path or in the background. Use for: vocabulary and design choices for saving things between sessions.

## Wisdom (Communities)

- Local: your university makerspace staff and your design-review faculty advisor
  Use for: checking which questions students really ask and which facts (training status, machine rules) must be exact.
