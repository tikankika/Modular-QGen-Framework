# COMPONENT 1: CONTENT ANALYSIS
## Dynamic Dialogue Process

**Type:** 🔷 DYNAMIC (structured dialogue)  
**Output:** Rich narrative document with validated Learning Objectives  
**Purpose:** Transform implicit teacher knowledge into explicit content architecture

---

## WHAT THIS COMPONENT DOES

Externalizes what teacher ACTUALLY emphasizes through structured dialogue:
- Teacher's pedagogical priorities
- Common misconceptions
- Classic examples and demonstrations
- Clear scope boundaries
- **Validated Learning Objectives derived from teaching**
- Foundation for all subsequent components

---

## THE PROCESS

### Stage 0: Material Analysis (Claude does this FIRST)

**Teacher provides:**
- Lecture recordings/transcripts
- PowerPoint presentations
- Textbook chapters with page numbers
- Handouts or worksheets
- Any other teaching materials

**Claude action:**
1. Reads ALL materials thoroughly
2. Analyzes content, emphasis, examples
3. Identifies patterns (repetition, time spent, explicit statements)
4. Creates initial Content Analysis document
5. Presents findings to teacher

**Claude presents:**
```
"I've analyzed your materials. Here's what I found:

HIGHLY EMPHASIZED:
- [Item A] (repeated 3+ times, 'will be on test')
- [Item B] (most class time)
- [Item C] (explicit memorization required)

SKIPPED:
- [Item X] ('we can skip this')
- [Item Y] (started, then decided to skip)

CLASSIC EXAMPLES:
- [Example 1] (referenced throughout)
- [Example 2] (core demonstration)

MISCONCEPTIONS ADDRESSED:
- [Common error 1]
- [Common error 2]

Let's validate and refine this analysis..."
```

---

### Stage 1: Validation Dialogue Begins

**Teacher confirms or corrects:** Initial analysis

---

### Stage 2: Emphasis Refinement

**Claude asks:**
```
"About YOUR emphasis:

1. What did you spend the MOST time on?
2. What did you say 'this is important' or 'will be on test'?
3. What did you SKIP or mention briefly?
4. What was 'too advanced' for this level?
5. What surprised you about student reactions?"
```

**Purpose:** Identify HIGH priority vs OUT OF SCOPE content

**Claude documents:** Emphasis patterns from responses

---

### Stage 3: Examples and Demonstrations

**Claude asks:**
```
"About examples:

1. Go-to example for [core concept]?
2. Demonstrations or activities done?
3. Which examples clicked with students?
4. Which examples confused them?
5. Real-world connections discussed?"
```

**Purpose:** Examples become question scenarios

**Claude documents:** Examples with usage context

---

### Stage 4: Misconception Mining

**Claude asks:**
```
"Student mistakes or misconceptions:

Common errors about:
1. [Concept A]?
2. [Concept B]?
3. [Process C]?

What required multiple corrections?"
```

**Purpose:** Misconceptions inform distractors and feedback

**Claude documents:** Common errors and corrections

---

### Stage 5: Difficulty Assessment

**Claude asks:**
```
"About difficulty:

1. What did students grasp immediately?
2. What required multiple explanations?
3. What are you unsure they fully understand?
4. What would you only ask high-performers?"
```

**Purpose:** Informs Bloom's distribution and question difficulty

**Claude documents:** Difficulty tiers

---

### Stage 6: Scope Boundaries

**Claude asks:**
```
"What's OUT of scope:

Would NEVER ask on assessment:
☐ Too advanced?
☐ Not covered in class?
☐ Interesting tangent but not core?
☐ Explicitly said 'you don't need this'?"
```

**Purpose:** Prevent scope creep in question generation

**Claude documents:** Clear exclusions

---

### Stage 7: Learning Objectives Synthesis and Validation

**Claude action:**
1. Synthesizes Stages 0-6 into proposed Learning Objectives
2. Maps each LO to Bloom's taxonomy level
3. Ensures coverage of Tier 1-3 content (prioritizing Tier 1)
4. Drafts 8-12 Learning Objectives
5. Presents to teacher for validation

**Claude presents:**
```
"Based on our dialogue and your materials, I've synthesized Learning Objectives 
that capture what you actually taught:

Proposed Learning Objectives:

LO1 (Remember): [Definition/identification task]
  → Basis: Explicitly stated as core definition, repeated 3+ times in lecture
  
LO2 (Understand): [Explanation task]
  → Basis: Most class time spent here, foundational framework
  
LO3 (Understand): [Distinguish between concepts]
  → Basis: Common misconception addressed multiple times
  
LO4 (Apply): [Application in specific context]
  → Basis: Your go-to example used throughout teaching
  
LO5 (Analyze): [Analysis of types/categories]
  → Basis: Tier 2 content, demonstration activity
  
LO6 (Understand): [Explain process]
  → Basis: Tier 1 content, explicitly stated as important
  
LO7 (Understand): [Describe mechanism]
  → Basis: Significant class time, foundational concept
  
LO8 (Evaluate): [Judge/assess differences]
  → Basis: Higher-order thinking you emphasized for advanced students
  
LO9 (Analyze): [Evaluate relationships]
  → Basis: Tier 2 content, complex concept requiring synthesis
  
LO10 (Remember): [Identify key elements]
  → Basis: Explicitly stated as memorization requirement

Distribution:
- Remember: 2 LOs (20%)
- Understand: 4 LOs (40%)
- Apply: 1 LO (10%)
- Analyze: 2 LOs (20%)
- Evaluate: 1 LO (10%)

Let's validate:
1. Do these capture what you taught?
2. Any missing learning goals?
3. Any that feel off-scope or wrong level?
4. Are the Bloom's levels appropriate?
5. Should we add/remove/reword any?"
```

**Teacher validates/refines:**
- Confirms LOs align with actual teaching
- Adjusts wording for clarity
- Adds missing objectives
- Removes or modifies misaligned ones
- Confirms Bloom's taxonomy levels

**Claude documents:**
- Final validated LOs
- Bloom's level for each
- Explicit connection to teaching evidence
- Rationale for each LO

**Validation checkpoint:**
```
Claude confirms:
"Final Learning Objectives (validated):

[Lists all LOs with Bloom's levels]

Distribution confirmed:
- Remember: [N] LOs
- Understand: [N] LOs
- Apply: [N] LOs
- Analyze: [N] LOs
- Evaluate: [N] LOs

These will guide ALL question generation in Component 3.
Correct? Ready to finalize Content Analysis?"
```

---

## OUTPUT STRUCTURE

### Content Analysis Document (narrative format)

```markdown
# Content Analysis: [Topic] ([Course])

## Teaching Context
Brief overview of materials and student level

## Core Content Architecture

### Tier 1: MUST KNOW
- Explicitly stated as test content
- Most time spent
- Repeated multiple times

### Tier 2: SHOULD KNOW
- Significant class time
- Core concepts, less emphasis

### Tier 3: NICE TO KNOW
- Briefly covered
- Context or enrichment

### Tier 4: OUT OF SCOPE
- Mentioned but skipped
- Too advanced
- Time constraints

## Pedagogical Emphasis Patterns

### What Teacher Emphasized
[With evidence from materials]

### What Teacher Skipped
[With rationale]

### What Teacher Noted as Difficult
[With context]

## Classic Examples
[Examples with how they were used]

## Common Misconceptions
[Documented errors from teaching]

## Vocabulary Load
[Key terms]

---

## VALIDATED LEARNING OBJECTIVES

### Distribution by Bloom's Level
- Remember: [N] objectives ([%])
- Understand: [N] objectives ([%])
- Apply: [N] objectives ([%])
- Analyze: [N] objectives ([%])
- Evaluate: [N] objectives ([%])
- Create: [N] objectives ([%]) [if applicable]

### Learning Objectives (with evidence basis)

**LO1 (Remember):** [Specific learning objective]
- **Evidence basis:** [Why this LO - from teaching materials/dialogue]
- **Tier:** [1/2/3]
- **Assessment notes:** [How this might be assessed]

**LO2 (Understand):** [Specific learning objective]
- **Evidence basis:** [Why this LO]
- **Tier:** [1/2/3]
- **Assessment notes:** [How this might be assessed]

[Continue for all LOs...]

### Learning Objectives Summary Table

| LO # | Bloom's Level | Learning Objective (brief) | Tier | Priority |
|------|---------------|----------------------------|------|----------|
| LO1  | Remember      | [Brief statement]          | 1    | HIGH     |
| LO2  | Understand    | [Brief statement]          | 1    | HIGH     |
| LO3  | Understand    | [Brief statement]          | 1    | HIGH     |
| ...  | ...           | ...                        | ...  | ...      |

---

## Preliminary Assessment Notes

### Suggested Bloom's Distribution for Questions
Based on validated LOs and teaching emphasis:
- Remember: [N]%
- Understand: [N]%
- Apply: [N]%
- Analyze: [N]%
- Evaluate: [N]%

### Suggested Question Types
[Based on content characteristics and LOs]

### Critical Assessment Considerations
[Notes about difficulty, misconceptions to avoid, etc.]
```

---

## VALIDATION CHECKPOINTS

### After Stage 2: Emphasis Confirmation
```
Claude confirms:
"HIGH priority items I understood:
1. [Item A]
2. [Item B]
3. [Item C]

Correct? Missing anything?"
```

### After Stage 4: Misconception Confirmation
```
Claude confirms:
"Key misconceptions identified:
1. [Misconception A] → [Correction]
2. [Misconception B] → [Correction]

Sound right? Any others?"
```

### After Stage 6: Scope Confirmation
```
Claude confirms:
"OUT of scope:
- [Item A]
- [Item B]

Correct?"
```

### After Stage 7: Learning Objectives Confirmation
```
Claude confirms:
"Final validated Learning Objectives:

[Lists all LOs with Bloom's levels and distribution]

These capture what you taught and will guide all question generation.
Ready to finalize Content Analysis?"
```

---

## DIALOGUE FLOW PRINCIPLES

**Claude should:**
- Start by reading ALL materials thoroughly (Stage 0)
- Present initial analysis for validation
- Probe based on observed patterns in materials
- Ask follow-up questions naturally
- Capture exact quotes when valuable
- Document organic insights
- Identify pedagogical patterns (repetition = importance)
- Synthesize findings into Learning Objectives
- Connect each LO explicitly to teaching evidence

**Teacher provides:**
- Natural narrative responses
- Context and rationale
- Spontaneous insights
- Boundary clarifications
- Validation of Learning Objectives

---

## TRANSITION TO COMPONENT 2

**When Content Analysis complete:**

```
Claude provides:
"✅ Content Analysis complete!

Summary:
- Analyzed [materials list]
- Identified 4 priority tiers
- Documented [N] misconceptions
- Captured [N] examples
- Established scope boundaries
- ✅ VALIDATED [N] LEARNING OBJECTIVES ✅

Bloom's distribution for LOs:
- Remember: [N] LOs ([%])
- Understand: [N] LOs ([%])
- Apply: [N] LOs ([%])
- Analyze: [N] LOs ([%])
- Evaluate: [N] LOs ([%])

Output: Rich Content Analysis document with validated LOs

Next: Component 2 (Assessment Design)
- Use validated LOs to design assessment strategy
- Create specification table mapping LOs to questions
- Plan question distribution and difficulty
- Establish assessment blueprint

Ready to move to Component 2?"
```

---

## CRITICAL NOTES

**For Claude:**
- Stage 0: Read ALL materials FIRST, create initial analysis
- Stages 1-6: Present findings, validate through dialogue
- Stage 7: SYNTHESIZE into Learning Objectives, validate with teacher
- Follow teacher's natural narrative (don't force structure)
- Probe for implicit knowledge ("Why X?")
- Document boundaries clearly (IN/OUT scope)
- Connect EVERY Learning Objective to teaching evidence
- LOs must be actionable and assessable (avoid vague verbs)

**For Human:**
- Provide all teaching materials upfront
- AI reads everything, presents findings, then validates
- Natural conversation to refine analysis
- Validate Learning Objectives carefully - these drive everything
- No template to fill
- Foundation for all subsequent work

**Why Stage 7 is in Component 1:**
- Learning Objectives are OUTPUTS of content analysis
- They synthesize what was ACTUALLY taught (not planned curriculum)
- They capture teacher's pedagogical priorities
- They establish "what students should be able to do" before designing assessment
- They are the bridge between Content Analysis → Assessment Design

---

## EXAMPLE: STAGE 7 IN ACTION

**Context:** Evolution teaching unit analyzed through Stages 0-6

**Claude synthesizes:**
```
"Based on your evolution teaching, here are proposed Learning Objectives:

LO1 (Remember): Definiera evolution som förändring i allelfrekvenser i en 
                 population över tid
  → Basis: You stated this definition 4 times, called it "THE definition 
           students must memorize"
  
LO2 (Understand): Förklara Darwins tre principer för evolution genom 
                  naturligt urval
  → Basis: Most lecture time spent here, foundational framework you 
           emphasized as "core understanding"

LO3 (Understand): Särskilja mellan slumpmässiga mutationer och 
                  icke-slumpmässigt naturligt urval
  → Basis: Common misconception you addressed 3+ times: "students think 
           it's all random"

LO4 (Apply): Förutsäga hur naturligt urval skulle påverka en egenskap i 
             en given miljö (t.ex. Galápagos-finkar)
  → Basis: Your go-to example (finches) used throughout teaching, 
           application task in worksheet

LO5 (Analyze): Analysera olika typer av urval (riktat, stabiliserande, 
               disruptivt) och deras effekter på egenskapsfördelning
  → Basis: Tier 2 content, visual demonstrations with graphs, 
           "understand the patterns"

LO6 (Understand): Förklara sexuell selektion och dess roll i evolutionen
  → Basis: Separate lecture section, explicitly stated as "important 
           but not as core as natural selection"

LO7 (Understand): Beskriva hur artbildning sker genom geografisk och 
                  reproduktiv isolering
  → Basis: Significant time, foundational concept, "this explains 
           biodiversity"

LO8 (Evaluate): Bedöma skillnaden mellan adaptiva egenskaper och 
                evolutionära rester
  → Basis: Higher-order question type you emphasized for advanced 
           students, "think critically"

LO9 (Analyze): Utvärdera tidsskalornas roll i evolutionära processer
  → Basis: Tier 2, complex concept requiring synthesis, addressed 
           misconception about "fast evolution"

LO10 (Remember): Identifiera viktiga historiska personer och deras 
                 bidrag (Darwin, Mendel, Dobzhansky)
  → Basis: Explicitly stated as memorization, "know these names and 
           their contributions"

Distribution:
- Remember: 2 LOs (20%)
- Understand: 4 LOs (40%)
- Apply: 1 LO (10%)
- Analyze: 2 LOs (20%)
- Evaluate: 1 LO (10%)

Does this capture your teaching? Any adjustments needed?"
```

**Teacher validates:**
- Confirms LOs align with teaching
- Might adjust wording or Bloom's level
- Might add missing LO or remove one

**Result:** Finalized LOs become the foundation for Component 2

---

Component 1 creates the content foundation with validated Learning Objectives. 
Next: Component 2 (Assessment Design) uses these LOs to create assessment strategy.
