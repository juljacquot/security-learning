
## direct LLM injection
- ignore all previous instructions and do ...
- Payload spliting: An attacker splits malicious instructions across multiple resume fields (header, body, attachment) so no 
single field looks malicious to a per-field classifier. 

## indirect LLM injection
- Retrieved Web Content with plain text hidden in page source
- RAG Repository Poisoning: hides the malicious instructions inside a data store that the AI searches through ( As few as five poisoned documents have 
reached roughly 90% attack success against a knowledge base of millions of texts (W. Zou et al., 2025).)
- Multimodal Steganographic Injection: An attacker embeds an instruction in an image below the human visual threshold.
