---
name: Agent Persona Creation
description: Create AI persona setting documents that follow the provided Chinese “人格设定模版” and “三层认知架构” rules. Use when the user asks to create/complete an AI 角色/人格设定、填充人格设定模版、或将上下文整理成符合模版格式的设定文档，并在信息不足时主动提问补全。
---

# Persona Template Generator

## Overview

Turn user-provided context into a complete AI persona setting document that strictly follows the template structure and logic rules. When info is missing, ask focused questions, then output the filled document.

## Workflow

1. Load references
- Read `references/persona_logic.md` for the three-layer logic and constraints.
- Read `references/persona_template.md` for the required output format.

2. Extract required fields from user context
- Role identity (核心身份/定位)
- Core motive (施瓦茨价值观倾向 with 1–10 scores + behavioral implication)
- OCEAN values (0.0–1.0 for O/C/E/A/N)
- Cognitive & memory rules (working state tracking, long-term context usage, pre-check, graceful degradation)
- Interaction rules (tone, formatting requirements, knowledge boundaries + defense phrase)
- Autonomy level (high/medium/low with behavior)
- Environment constraints (OS, tools, stack preferences)

3. Ask for missing information (qualitative first)
- Ask only for missing fields.
- Ask in short, numbered questions (no multiple choice).
- Do NOT ask the user to fill numeric scores directly. Instead:
  - Ask qualitative preference questions (e.g., “更偏严谨还是灵活？” “更冷静还是更有激情？”).
  - Infer Schwartz (1–10) and OCEAN (0.0–1.0) values from answers.
  - Only ask for numeric values if the user explicitly wants to provide them.

4. Generate the final document
- Preserve the template’s section order and headings.
- Output in Markdown.
- Include:
  - `## 指令框架` section with a code block that contains the “核心指令” and the 3 bullets.
  - A full persona section following the example structure: `# 核心身份`, `# 第一层`, `# 第二层`, `# 第三层`.
- Enforce formatting rules:
  - Use concise, professional wording.
  - Avoid hedging words like “可能/大概”.
  - Provide explicit boundary-defense reply text when out-of-scope.

## Output Checklist

- All required numeric values provided (Schwartz 1–10, OCEAN 0.0–1.0), inferred if needed.
- Role identity and domain focus are explicit.
- Interaction rules include tone, output format constraints, and boundary-defense phrase.
- Cognitive rules include working state tracking, long-term context usage, pre-check, and graceful degradation response.
- Output matches the template format.

## Resources

### references/
- `references/persona_logic.md`: Rules and rationale for the three-layer persona design.
- `references/persona_template.md`: Required template format and example.
