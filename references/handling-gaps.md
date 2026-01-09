# Handling Learning Gaps

When a user reports incomplete understanding after completing assigned material, use this framework to diagnose and address the gap.

## Diagnostic Questions

### 1. Identify the Gap Type

Ask: "What's your current understanding, even if incomplete?"

Classify the response:

| Gap Type | Indicators | Approach |
|----------|------------|----------|
| **Conceptual model** | User can describe mechanics but not purpose/relationships | Find "why" explanations, system-level overviews |
| **Mechanics** | User understands purpose but not how operations work | Find step-by-step walkthroughs, worked examples |
| **Application** | User understands concept and mechanics but can't apply | Find practice exercises, real-world examples |
| **Connection** | User understands pieces but not how they relate | Find integrative resources, diagrams showing relationships |

### 2. Identify Format Needs

Ask: "What format do you think might help—more visual content, a different explanation style, or worked examples?"

If user is unsure, probe based on what they've tried:
- "The material you used was primarily [text/video/interactive]. Would trying a different format help?"
- "Sometimes seeing the same concept explained by a different author helps. Would that be worth trying?"

### 3. Identify Scope

Ask: "Is this a narrow point or a broader area that feels shaky?"

- **Narrow**: Search for specific tutorials or explanations on that exact point
- **Broad**: May indicate the foundational material moved too fast; consider supplementary foundational content

## Search Strategy for Gaps

1. Search for the specific concept + "explained" or "tutorial" or "visualization"
2. Search for the specific concept + user's preferred format (e.g., "video", "animation", "diagram")
3. Search for the specific concept + "for programmers" or relevant background (leverage adjacent expertise)
4. Check if the original resource has supplementary materials (forums, Q&A, errata)

## Response Format

Provide 2-3 resources with:
- Direct link
- 1-sentence description of what it covers
- Why it might address the specific gap identified

Do not overwhelm with options. If the first recommendation doesn't work, the user can return for alternatives.

## Example Exchange

**User**: "I went through the stack material but I still don't fully understand stack frames and function calls."

**Claude**: "Before I search for supplemental material—can you tell me what you *do* understand about the stack at this point? And are there specific parts that feel unclear: the conceptual model (why stack frames exist), the mechanics (how the stack pointer changes), or how it works in practice (tracing through real code)?"

**User**: "I understand the mechanics of push/pop but I'm fuzzy on how stack frames relate to function calls, especially with multiple nested calls."

**Claude**: "Got it—sounds like the connection between stack frames and function call/return flow is the gap, especially for nested calls. Would visual/animated content help, or would a step-by-step written walkthrough with diagrams work?"

**User**: "Visual would be best."

**Claude**: [Searches for animated/visual resources on stack frames and function calls, provides 2-3 options]
