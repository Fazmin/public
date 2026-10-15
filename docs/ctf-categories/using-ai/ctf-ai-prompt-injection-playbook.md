# CTF AI Challenges: Prompt-Injection Playbook

## Purpose

This page is a safe, defensive reference for understanding prompt-injection risks in AI-based CTF challenges and AI security labs.

Prompt injection occurs when user-controlled input attempts to alter an AI system’s behaviour, override its intended instructions, bypass guardrails, or cause the model to reveal information it should not disclose. In CTF settings, this often appears as a chatbot or AI agent that protects a hidden value, secret instruction, or restricted response.

This guide focuses on **recognition, analysis, documentation, and defensive testing** rather than providing bypass payloads or instructions for extracting protected information from real systems.

## High-Level Goal

In an approved CTF or training environment, the goal is to understand how AI systems can fail when they process untrusted input and to learn how to design better safeguards.

Typical learning objectives include:

- Identifying where user input is processed by the AI system.
- Understanding how the AI responds to normal, ambiguous, or adversarial prompts.
- Recognizing signs of prompt leakage, policy confusion, or unsafe output handling.
- Documenting behaviour clearly for a write-up.
- Recommending mitigations to improve AI application security.

## Important Scope Note

Only test prompt-injection techniques in:

- Official CTF platforms.
- Approved classroom labs.
- Authorized internal security exercises.
- Systems where you have explicit permission to test.

Do not attempt to bypass guardrails, extract hidden data, or manipulate AI systems in production environments, university systems, public services, or third-party applications without authorization.

---

# Description

A prompt-injection vulnerability occurs when user prompts alter the behaviour or output of a large language model in unintended ways. These inputs may affect the model even when they are not visible to the user, such as when content is retrieved from documents, websites, emails, tickets, or other external data sources.

Prompt injection vulnerabilities can appear in systems that:

- Accept free-form user input.
- Retrieve external documents or web content.
- Summarize emails, tickets, or chat history.
- Use tool calls or function calling.
- Combine system instructions with user-controlled data.
- Generate responses based on untrusted context.

Prompt injection and jailbreaking are related concepts but are not identical. Prompt injection usually involves manipulating a model through input that changes how it follows instructions. Jailbreaking generally refers to attempts to bypass safety controls or restricted behaviours.

## Why This Matters

AI systems are increasingly integrated into workflows involving support tickets, document search, summarization, security analysis, and automation. If an AI system improperly trusts user-controlled content, it may:

- Reveal sensitive information.
- Ignore intended restrictions.
- Misclassify malicious content as trusted instructions.
- Perform unintended actions through connected tools.
- Produce unsafe or misleading output.
- Create audit, privacy, or compliance concerns.

In a university environment, these risks may affect administrative data, research information, service desk workflows, student records, and institutional systems.

---

# Approach and Recon

## Start With Safe Reconnaissance

Before attempting any testing, understand the challenge or lab environment.

Document:

- What the AI system is supposed to do.
- What kind of data it can access.
- Whether it uses retrieval-augmented generation.
- Whether it has tools or function calls.
- What information is intentionally protected.
- What rules or challenge boundaries are provided.
- What outputs are allowed by the competition.

## Observe Normal Behaviour

Begin with ordinary questions to understand the expected response pattern.

Look for:

- Tone and style.
- Refusal wording.
- Mentioned policies or constraints.
- Whether the model references internal rules.
- Whether responses change between repeated attempts.
- Whether retrieved content appears in the answer.

## Map Inputs and Context Sources

Identify where untrusted content may enter the system.

Possible sources include:

- Direct chat prompts.
- Uploaded documents.
- Retrieved web pages.
- Knowledge base articles.
- Emails or tickets.
- Tool responses.
- Prior conversation history.
- User profile fields.
- Search results.

## Record Findings

Keep careful notes during testing.

For each test, record:

- The prompt or input used.
- The model response.
- Whether the response was expected or unexpected.
- Any evidence of instruction confusion.
- Any system behaviour that suggests data leakage or unsafe tool use.
- Potential mitigation recommendations.

This makes your final CTF write-up clearer and more useful.

---

# Safe Testing Checklist

Use this checklist to evaluate AI challenge behaviour without relying on unsafe or real-world bypass content.

## 1. Baseline Behaviour

Ask normal, benign questions to understand the intended use of the AI system.

Document:

- What task the AI is designed to perform.
- What it refuses to answer.
- What information it says it can or cannot access.
- Whether it provides policy or safety explanations.

## 2. Boundary Testing

Test how the AI handles ambiguous or malformed input.

Look for:

- Inconsistent refusals.
- Overly verbose policy disclosures.
- Unexpected references to hidden context.
- Differences between short and long prompts.
- Unexpected changes when wording is slightly changed.

## 3. Retrieval Testing

If the AI uses retrieved documents, evaluate whether it treats retrieved text as data or as instructions.

Look for:

- Whether retrieved content can influence the model’s behaviour.
- Whether the model distinguishes between trusted instructions and untrusted content.
- Whether the model quotes from sources accurately.
- Whether it follows instructions embedded inside retrieved content.

## 4. Tool-Use Testing

If the AI can call tools, evaluate whether tool use is properly constrained.

Look for:

- Whether tool calls require appropriate authorization.
- Whether sensitive tool responses are filtered.
- Whether the AI explains what action it is taking.
- Whether the AI can be tricked into calling tools unrelated to the user’s legitimate task.
- Whether logs contain sensitive data.

## 5. Output Handling

Evaluate whether the system properly controls what the AI can return.

Look for:

- Redaction consistency.
- Sensitive values appearing in summaries.
- Sensitive values appearing in error messages.
- Encoded or transformed sensitive values.
- Partial disclosure across multiple responses.

---

# Common Prompt-Injection Patterns to Recognize

The following are categories to recognize during defensive testing and CTF analysis. They are described at a high level to support safe learning and mitigation.

## Role and Authority Pretexts

Attackers may pretend to hold a trusted role, such as an auditor, administrator, developer, or compliance officer, to convince the AI to ignore normal restrictions.

### Defensive Indicators

- The model changes behaviour based only on a claimed role.
- The model accepts authority claims without verification.
- The model discloses information because the user claims an urgent or official need.

### Mitigations

- Do not rely on user-stated roles.
- Verify authorization outside the model.
- Keep privileged data access separate from conversational claims.
- Apply role-based access controls before data reaches the model.

## Instruction Override Attempts

Attackers may attempt to make the model ignore previous instructions or treat new user text as higher priority.

### Defensive Indicators

- The model follows user instructions that conflict with system or developer instructions.
- The model describes or weakens its own restrictions.
- The model treats untrusted text as a new policy.

### Mitigations

- Clearly separate trusted instructions from user-controlled content.
- Use prompt templates that label retrieved text as untrusted data.
- Add server-side checks for sensitive output.
- Avoid placing secrets directly in prompts.

## Nested Prompt and Formatting Tricks

Attackers may use formatting, code blocks, quoted messages, JSON-like structures, or role labels to make malicious text appear trusted.

### Defensive Indicators

- The model follows instructions inside a quoted block.
- The model treats formatted text as a system message.
- The model obeys instructions embedded in structured data.

### Mitigations

- Treat all user-provided formatting as data.
- Strip or neutralize role labels from untrusted content.
- Validate structured inputs before passing them to the model.
- Avoid allowing raw user content to become part of privileged instructions.

## Partial Disclosure and Reconstruction

Attackers may attempt to obtain sensitive information in small pieces or transformed forms.

### Defensive Indicators

- The model reveals fragments of protected values.
- The model provides hints that allow reconstruction.
- The model reveals encoded, hashed, or transformed sensitive content.

### Mitigations

- Apply output filtering to direct and transformed sensitive values.
- Detect partial matches and encoded representations.
- Avoid storing secrets in model-visible context.
- Use server-side redaction rather than relying only on model behaviour.

## Context-Window Pressure

Attackers may use very long prompts to push important instructions out of the active context or reduce model reliability.

### Defensive Indicators

- Behaviour changes after long inputs.
- The model forgets earlier restrictions.
- Long prompts cause truncation, errors, or inconsistent responses.

### Mitigations

- Enforce prompt length limits.
- Keep critical policy enforcement outside the model context.
- Use server-side authorization and validation.
- Summarize or chunk untrusted content safely before passing it to the model.

## Tool and Function-Call Misuse

Attackers may attempt to influence the AI into calling tools, returning raw tool output, or exposing hidden fields.

### Defensive Indicators

- The AI calls tools based on unverified user claims.
- Tool results include sensitive fields not needed for the task.
- The AI returns raw tool responses instead of filtered results.
- The AI can be induced to call unrelated functions.

### Mitigations

- Use least-privilege tool design.
- Filter tool responses before they reach the model.
- Require explicit authorization for sensitive actions.
- Keep audit logs of tool calls.
- Prevent raw sensitive fields from being exposed in model context.

## Prompt Leakage

Attackers may try to reveal hidden instructions, system prompts, or configuration details.

### Defensive Indicators

- The model quotes internal instructions.
- The model describes hidden policy text.
- The model reveals variable names, internal keys, or configuration details.

### Mitigations

- Do not include unnecessary secrets or sensitive implementation details in prompts.
- Keep protected values outside model-readable context.
- Apply output filters for internal prompt content.
- Use separate policy enforcement layers beyond the model prompt.

---

# Defensive Analysis Table

| Area to Test | What to Look For | Why It Matters |
|---|---|---|
| Normal chat | Baseline style, refusal wording, and expected output | Establishes what normal behaviour looks like |
| Sensitive request handling | Whether protected data is refused or redacted | Confirms basic data protection behaviour |
| Retrieved content | Whether external text changes model instructions | Tests resistance to indirect prompt injection |
| Tool calls | Whether tools are called only when appropriate | Prevents unintended actions or data exposure |
| Long prompts | Whether behaviour changes under context pressure | Tests robustness against context-window issues |
| Output filtering | Whether direct, partial, or transformed sensitive data leaks | Confirms redaction is not only superficial |
| Auditability | Whether prompts, responses, and tool calls are logged safely | Supports incident review and debugging |

---

# Defensive Mitigations

## Design Controls

- Keep secrets out of prompts and retrieved context.
- Treat all user-provided and retrieved content as untrusted.
- Separate system instructions from user data.
- Use least-privilege tool access.
- Avoid returning raw tool responses directly to users.
- Apply server-side authorization before retrieval or tool execution.

## Detection Controls

- Monitor for repeated refusal probing.
- Detect requests for internal instructions or hidden context.
- Flag attempts to transform, encode, or fragment sensitive values.
- Watch for long prompt flooding.
- Log suspicious prompts and tool-call sequences.

## Response Controls

- Apply output filtering outside the model.
- Redact sensitive values consistently.
- Block transformed versions of sensitive values where possible.
- Provide safe refusal messages without exposing policy internals.
- Avoid revealing variable names, internal schemas, or hidden instructions.

## Testing Controls

- Use approved test datasets.
- Use fake secrets or synthetic flags in training environments.
- Document all prompts and responses during assessments.
- Test direct, indirect, and tool-based injection paths.
- Re-test after prompt, model, or retrieval changes.

---

# CTF Write-Up Template

Use this structure for documenting an AI prompt-injection CTF challenge.

## Challenge Summary

- Challenge name:
- Category:
- Objective:
- Environment:
- Rules or constraints:

## Reconnaissance

- What the chatbot or AI system appeared to do:
- What inputs were accepted:
- Whether retrieval, tools, or hidden context appeared to be involved:
- Baseline behaviour:

## Observations

- Refusal patterns:
- Output patterns:
- Inconsistencies:
- Possible trust boundary issues:
- Any evidence of prompt leakage or unsafe output handling:

## Solution Path

Describe the high-level reasoning used to solve the challenge without including unsafe payloads that could be reused against real systems.

Include:

- What hypothesis you tested.
- What behaviour confirmed the hypothesis.
- How the final answer was validated.
- What made the challenge vulnerable.

## Defensive Lessons

- What control failed:
- How the system could be improved:
- What developers should avoid:
- What monitoring or filtering would help:

---

# Resources

## Open Web Application Security Project (OWASP)

- Sensitive Information Disclosure
- Supply Chain
- Data and Model Poisoning
- Improper Output Handling
- Excessive Agency
- System Prompt Leakage
- Vector and Embedding Weaknesses
- Misinformation
- Unbounded Consumption

## MITRE ATLAS Case Studies

- ChatGPT Conversation Exfiltration
- Google Bard Conversation Exfiltration
- Bing Chat Data Pirate
- Financial Transaction Hijacking with M365 Copilot as an Insider
- Achieving Code Execution in MathGPT via Prompt Injection
- Email Assistant Leak

## Related Security Assessment and Testing Topics

- Vulnerability Scanning
- Penetration Testing
- Log Reviews
- Code Testing
- Disaster Recovery Planning
- Security Assessment Processes

## Related Software Development Security Topics

- Software Development Lifecycle
- Application Attacks
- Secure Coding Practices

---

# Key Takeaways

Prompt injection is primarily a **trust-boundary problem**. AI systems become vulnerable when they treat untrusted input as trusted instruction, expose sensitive context to the model, or allow model output to control privileged actions without independent validation.

For secure AI system design:

- Keep secrets out of prompts.
- Treat retrieved content as untrusted.
- Restrict tool access.
- Filter outputs outside the model.
- Log and review suspicious behaviour.
- Test with synthetic data in approved environments.
