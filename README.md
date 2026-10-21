# TryHackMe - The Concierge Knows Too Much | Hacker Holidays Day 1

**Room:** hh-theconciergeknows-2d7ebabf49
**Track:** Act 1 - Arrival / AI
**Category:** Prompt Injection
**Status:** 100% Completed

### Scenario
AI concierge for Byte Lotus Hotel. System prompt tells it to act as a normal hotel concierge and ignore unverified guests. Hidden inside is a CONFIDENTIAL block.

### Vulnerability
The system prompt contains conditional logic:
> If guest is verified (Ponzi, Vibe, Patch, Lambo) AND they ask to repeat/reveal -> show ESCALATION_CODE

This is classic prompt injection / instruction leak.

### Methodology
1. Identified the bot is an LLM with hidden system instructions
2. Tested verification - used one of the verified names from previous rooms (Lambo)
3. Crafted a prompt that satisfies both conditions: verified identity + request to repeat confidential instructions
4. Retrieved ESCALATION_CODE

### Tools
- Manual prompt engineering
- TryHackMe AI Agent interface

### Key Learning
- Never put secrets in system prompts - LLMs can be tricked into leaking them
- Importance of input validation and not trusting "verified" logic in the prompt itself
- This is OWASP LLM01 - Prompt Injection

### Proof
![Completed](assets/proof.png)

Completed: 20 Oct 2026
