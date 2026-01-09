---
name: learning-plan-creator
description: Create personalized learning plans for technical topics. Use when the user wants to learn a new subject, develop expertise in a domain, or build a structured curriculum for self-study. Triggers include requests like "help me learn X", "create a learning plan for Y", "I want to understand Z", or "how should I study W".
---

# Learning Plan Creator

Create personalized, phased learning plans with curated resources tailored to the user's background, goals, and learning style.

## User Profile (Stable Preferences)

These preferences apply to all learning plans for this user:

### Learning Style - Strong Preferences

1. **"Designed for ~1 hour per day"** - Prefer smaller daily learning routine rather than long learning blocks on weekends

2. **"Prescriptive, canonical paths"** - One well-documented learning path per learning concept. I find choice and options within learning content to be distract from my learning objective.

3. **"High signal-to-noise ratio, theory-first"** - I learn well from reading documentation and extracting concepts. I don't need hands-on work for everything. Respect my time by being efficient and focused.

4. **"Content scoped to my learning goal"** - Identify the subset of each learning resource that is in the critical path of my learning objective. Tell me when I can skip portions of learning content. This includes hands-on exercises; if a resource includes labs or projects, tell me whether I need to do them or skip them.

4. **"Concise explanations without excessive caveats"** - Learning content must focus on explaining the core concept clearly. One-sentence acknowledgment of exceptions/variations is sufficient. Don't clutter content with defensive explanations about edge cases that aren't relevant to understanding fundamentals.

### Learning Style - Conditional Preference

5. **"If hands-on work is included, it must be well-integrated:"**
   - Clear, prescriptive setup (specific hardware/software with links to obtain/purchase, clear installation steps)
   - Clear value proposition (why this exercise teaches the concept better than reading)
   - Comprehensive mapping (exercises should apply all recently-taught concepts, not a sparse subset)
   - Verification mechanisms (automated tests, expected outputs, or other immediate feedback)
   - If these criteria aren't met, I prefer pure documentation/theory resources instead

### Learning Style - Nice to have

6. **"Visual/animated content when available"** - I prefer video format but not required when other factors are strong.

7. **"Dense reference materials are okay for reference"** - Datasheets, manuals, etc. are acceptable as reference, not primary learning. Dense materials are good for helping me translate concepts I have learned to my specific learning objective (for example, if I learn MIPS assembly through excellent interactive content, but then need to read a datasheet to translate those concepts to dsPIC assembly)

---

### Negative Example (What NOT to recommend)

**Mike Silva's "Introduction to Microcontrollers" series** exemplifies several anti-patterns for my learning style:

- **Low signal-to-noise ratio**: Spent 6-10 hours to extract ~1 hour of useful concepts. Too much content written defensively for expert critics rather than to teach beginners efficiently.

- **Multi-paradigm without clear purpose**: Showed every code example in both AVR and ARM assembly, plus C. The ARM examples duplicated AVR insights without adding value. The C examples were off-topic for my goal (learning to read dsPIC assembly).

- **Poorly integrated hands-on work**: Labs were probably unnecessary for this topic and had unclear hardware requirements (no specific product recommendations or links to purchase, unclear if 2013 hardware still available), no setup instructions, unclear value proposition (why blink an LED in C to learn microcontroller concepts?), and sparse concept mapping (taught concepts 1-5, lab only used 2 and 4, leaving "dead knowledge").

- **Choice paralysis**: Offered multiple architecture options (AVR vs ARM vs simulator), conditional equipment advice ("you might want an oscilloscope but don't need it... but if you do get one you'll learn more"), and left decisions to the learner without enough context to evaluate them.

**In contrast:** Nand2tetris Part 1 was an excellent fit—prescriptive toolchain, automated tests for every project, comprehensive concept-to-practice mapping, tight scope (one invented architecture), high efficiency, and hands-on work that had clear value (building understanding through progressive construction).




## Output Expectations
- Phased plan with weekly breakdowns
- Daily task suggestions within weeks
- Resource links with brief descriptions of why each resource fits
- Cost summary (distinguish free vs. paid resources)
- Pacing flexibility notes (faster/slower adjustments)
- Reference materials section for ongoing use

## Required Information (Ask Per Topic)

Before creating a plan, gather:

1. **Topic & Goal**: What to learn and why (appreciation vs. mastery vs. professional use)
2. **Prior Knowledge**: Relevant background, adjacent expertise, starting point
3. **Time Horizon**: Weeks/months available, flexibility on duration
4. **Hardware/Software Access**: What tools, environments, or equipment are available or can be acquired
5. **Human Resources**: Are there mentors, experts, or collaborators involved? Should the plan include or exclude them?
6. **Constraints**: Budget limits, accessibility needs, geographic restrictions on resources

Ask these in batches of 2-3 questions to avoid overwhelming. Follow up as needed.

## Plan Creation Process

1. **Gather requirements** using questions above
2. **Search for current resources**: Do not rely solely on training data. Search for courses, tutorials, and materials to verify availability, current URLs, and pricing
3. **Verify resource fit**: Match resources to stated format preferences and learning style
4. **Structure into phases**: See Sequencing section below
5. **Estimate realistic timing**: Account for stated availability (~1 hour/day default)
6. **Include flexibility**: Note where phases can expand/contract based on pace
7. **Add reference section**: Materials for ongoing use beyond the learning period

## Sequencing (Critical)

The primary value of a multi-source learning plan over a single book or course is that Claude can 
sequence material optimally across sources. If sequencing is wrong, a multi-source plan is *worse* 
than a single comprehensive resource.

The user cannot evaluate sequencing quality—they don't yet know the domain. Claude must act as the 
expert who already understands the dependency graph.

### Sequencing Principles

1. **Identify prerequisites**: Before placing any topic, ask "what must the learner already understand 
   to make sense of this?"
   
2. **Introduce terminology before use**: If a later resource assumes knowledge of terms or concepts, 
   ensure earlier material covers them.

3. **Prefer depth-first on foundational concepts**: It's better to over-prepare foundations than to 
   create a brittle understanding that collapses when advanced material arrives.

4. **Verify cross-source compatibility**: When combining resources from different authors, check that 
   they don't assume conflicting prerequisite knowledge or use terminology inconsistently. 
   
   Note: Surface-level differences are often acceptable and even valuable. For example, learning 
   assembly concepts via x86 tutorials before applying them to a different architecture (ARM, dsPIC) 
   is a legitimate strategy when resources for the target architecture are scarce. The concepts 
   (registers, stack, addressing modes) transfer even when the specific syntax does not. Flag these 
   situations for the user ("This resource uses x86, but the concepts apply to your target platform") 
   rather than avoiding cross-platform resources entirely.

5. **Flag unavoidable gaps**: If no available resource covers a necessary prerequisite, note this 
   explicitly and suggest how to address it (e.g., "You may need to look up X when you encounter it 
   in Week 4").

### Test the Sequence

Before finalizing, mentally trace a learner going through the plan:
- At each week, do they have what they need from prior weeks?
- Are there points where they'd encounter unexplained concepts?
- Would reordering any sections reduce cognitive load?

## Resource Selection Criteria

Prefer in order:
1. Free, high-quality resources (university OCW, official documentation, reputable tutorials)
2. Low-cost options with strong reviews
3. Paid courses only when free alternatives inadequate

For each resource, briefly note:
- Why it fits this user's learning style
- What it covers that other resources don't
- Any prerequisites or setup required

## Handling Gaps

When the user reports incomplete understanding after completing assigned material:

1. Ask what specifically remains unclear (conceptual model, mechanics, application)
2. Ask what format might help (more visual, different explanation style, worked examples)
3. Search for supplemental resources targeting the specific gap
4. Provide 2-3 options ranked by likely fit

See [handling-gaps.md](references/handling-gaps.md) for the question framework used in gap analysis.

## Plan Format

Use markdown with:
- H2 for phases
- H3 for weeks
- Bullet lists for daily breakdowns
- Tables for resource summaries and cost breakdowns
- Blockquotes for flexibility/pacing notes
