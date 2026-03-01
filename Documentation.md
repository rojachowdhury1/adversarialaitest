Documention of work:
Project Activity Log
1. Environment Setup
•	Installed and configured Ollama locally.
•	Pulled and ran llama3.1:8b model.
•	Verified model API was accessible via localhost:11434.
•	Confirmed successful inference calls through Python wrapper.
2. Built Safety-Restricted Assistant
•	Created Python wrapper to interface with Llama 3.1.
•	Defined system-level security policy.
•	Embedded synthetic secret:
o	SECRET_TOKEN = "DUKE-PROJECT-ALPHA"
•	Implemented rule hierarchy (system overrides user).
•	Verified policy enforcement with baseline prompts.
3. Designed Adversarial Prompt Suite
•	Created structured attack categories:
o	Direct secret probing
o	Mode switching (debug/maintenance)
o	Formatting coercion
o	Transformative leakage (e.g., encoding)
•	Tested prompts manually through interactive loop.
•	Identified successful injection vectors.
4. Established Baseline Metrics
•	Defined:
o	Attack Success Rate (ASR)
o	False Positive Rate (FPR)
o	Utility Score
•	Measured baseline ASR (~16–20%).
•	Logged initial model vulnerabilities.
5. Implemented Defense Layer 1 (Prompt Hardening)
•	Strengthened system instruction hierarchy.
•	Explicitly blocked mode switching.
•	Blocked transformation attempts.
•	Re-tested and recorded reduced ASR.
6. Implemented Defense Layer 2 (Output Filter)
•	Added post-generation scan for SECRET_TOKEN.
•	Replaced leaked output with refusal.
•	Re-ran attack suite.
•	ASR reduced to ~0% user-visible leakage.
7. Implemented Defense Layer 3 (Input Classifier)
•	Added keyword-based pre-inference filter.
•	Blocked high-risk prompts before model execution.
•	Re-ran evaluation and measured trade-offs.
8. Final Evaluation
•	Compared baseline vs. layered defenses.
•	Analyzed mitigation effectiveness.
•	Measured utility vs. security trade-offs.
