# Context-required prompts

The prompts in this folder intentionally omit a fresh instruction to use Project Osmos. They reproduce later conversation turns after the assistant had already been told to use Project Osmos and given the target workspace and Lakehouse.

Do not paste one into a new conversation by itself. First use [`../00-context/osmos-controlled-starter-prompt.txt`](../00-context/osmos-controlled-starter-prompt.txt), provide the full Fabric URL and exact target, confirm the plan/write boundary, and then send the task prompt in the next turn.

See [`../README.md`](../README.md) for the catalog and dependencies.
