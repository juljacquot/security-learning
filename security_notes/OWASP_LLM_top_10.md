# OWASP_LLM_top_10

My reading summary of https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/

## LLM01:2026 Prompt Injection

**prompt injection:** A prompt-injection vulnerability occurs when input to LLM alters the model's behavior in ways the application developer did not intend.

Interesting note: LLMs make no difference between instructions and user input data (interesting to read this: https://arxiv.org/html/2403.06833v1)

**direct prompt injection**: direct input
**indirect prompt injection:** The model ingests content from an external source (a web page, an email, an MCP server's output,that contains 
data which acts as prompt injection.

**example**: study showing that medical images can be altered to tell a model to never detect a tumor (https://www.nature.com/articles/s41467-024-55631-x)

Prevention:
- no real prevention exist against the injection itself. The real defence is to limit what the LLM rights (least privileged principles)

Limiting measures: 
- Constrain the model's role and capabilities in the system prompt. Use declarative allow and deny 
statements ("assist with X only, do not access Y, do not forward output to external addresses"), not 
open-ended grants.
- Define a strict output schema and validate every response in trusted application code
- Require explicit human confirmation before any privileged, irreversible, or externally visible 
action
- strip tag-block (U+E0000 to E007F), variation-selector (U+FE00 to FE0F), and zero-width 
(U+200B, U+200C, U+200D, U+2060) characters at every ingest and render boundary
