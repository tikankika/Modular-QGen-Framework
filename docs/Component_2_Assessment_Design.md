# COMPONENT 2: ASSESSMENT DESIGN
## Strategic Planning Process

**Type:** 🔷🔶 HYBRID (pedagogical decisions + framework structure)  
**Input:** Component 1 (Content Analysis)  
**Output:** Question Blueprint document  
**Purpose:** Transform content architecture into systematic assessment plan

---

## WHAT THIS COMPONENT DOES

Creates strategic plan for question generation:
- Learning Objectives from content analysis
- Question distribution (Bloom's, types, difficulty)
- Assessment strategy (formative/summative)
- Coverage validation
- Blueprint for Component 4 (Question Generation)

---

## THE PROCESS

### Stage 1: Learning Objective Creation

**Claude does:**
1. Analyzes Content Analysis (Component 1 output)
2. Identifies content in each tier (MUST/SHOULD/NICE/OUT)
3. Creates draft Learning Objectives
4. Maps LOs to Bloom's taxonomy

**Claude presents:**
```
"Based on Content Analysis, I propose [N] Learning Objectives:

REMEMBER (Factual knowledge):
- LO1: [Description]
- LO2: [Description]

UNDERSTAND (Conceptual understanding):
- LO3: [Description]
- LO4: [Description]

APPLY (Scenario application):
- LO5: [Description]

ANALYZE (Compare/contrast):
- LO6: [Description]

EVALUATE (Critical assessment):
- LO7: [Description]

Total: [N] Learning Objectives
Coverage: All Tier 1 content, most Tier 2

Missing anything? Should we add/remove/modify?"
```

**Teacher validates:** LOs complete and appropriate

---

### Stage 2: Assessment Strategy Decision

**Claude asks:**
```
"Assessment type:

FORMATIVE (practice, learning-focused):
- Low stakes
- Immediate feedback
- Multiple attempts
- Build confidence
Use when: Students need practice before exam

SUMMATIVE (graded, evaluation):
- High stakes
- Deferred/no feedback during test
- Limited attempts
- Measure achievement
Use when: Final evaluation needed

Which fits your purpose?"
```

**Teacher decides:** Formative or Summative

**Claude documents:** Assessment configuration

---

### Stage 3: Question Target

**Claude asks:**
```
"How many questions total?

Consider:
- Each LO needs 2-4 questions minimum
- [N] LOs × 3 questions average = [N×3] questions
- Time available: [X] minutes
- Rule of thumb: 1.5 minutes per question

Recommendation: [calculated target] questions

Your target?"
```

**Teacher decides:** Total question count

---

### Stage 4: Bloom's Distribution Planning

**Claude proposes:**
```
"Question distribution by Bloom's level:

For [FORMATIVE/SUMMATIVE] assessment:

Recommended:
- Remember: [%] ([N] questions) - Foundation
- Understand: [%] ([N] questions) - Core concepts
- Apply: [%] ([N] questions) - Scenarios
- Analyze: [%] ([N] questions) - Higher-order
- Evaluate: [%] ([N] questions) - Critical thinking

Rationale:
[Explanation based on assessment type and content]

Adjust these percentages?"
```

**Teacher adjusts:** Bloom's distribution

**Claude calculates:** Exact question counts per level

---

### Stage 5: Question Type Mix Planning

**Claude proposes:**
```
"Question types to use:

AUTO-GRADING (recommended for [type]):
- Multiple Choice (Single): [%] - Versatile
- Multiple Choice (Multiple): [%] - Complex understanding
- True/False: [%] - Quick checks
- Fill-in-Blank: [%] - Key terms
- Matching: [%] - Relationships

INTERACTIVE:
- Inline Choice: [%] - Context-based
- Gap Match: [%] - Process understanding

MANUAL GRADING:
- Text Area: [%] - Short response
- Extended Text: [%] - Essay

Based on your content and assessment type.

Adjust this mix?"
```

**Teacher adjusts:** Type distribution

---

### Stage 6: Difficulty Distribution

**Claude proposes:**
```
"Difficulty levels:

- Easy (basic recall, simple understanding): [%]
- Medium (application, developed reasoning): [%]
- Hard (analysis, evaluation): [%]

For [FORMATIVE]: More easy/medium (build confidence)
For [SUMMATIVE]: Balanced distribution (measure range)

Adjust?"
```

**Teacher adjusts:** Difficulty distribution

---

### Stage 7: Question Blueprint Creation

**Claude creates:**
```
"Question Blueprint:

[Table showing all questions]
Q# | LO | Bloom's | Type | Difficulty | Points
------------------------------------------------
Q1 | LO1 | Remember | Fill-blank | Easy | 1
Q2 | LO1 | Remember | MC-Single | Easy | 1
Q3 | LO2 | Understand | MC-Single | Medium | 2
...

Summary:
- Total questions: [N]
- Total points: [N]
- All LOs covered: ✅
- Distribution validated: ✅

Ready to proceed to Question Generation?"
```

**Teacher validates:** Blueprint complete

---

## OUTPUT STRUCTURE

### Question Blueprint Document

```markdown
# Question Blueprint: [Topic] ([Course])

## Assessment Configuration

**Type:** Formative/Summative
**Total Questions:** [N]
**Total Points:** [N]
**Time Limit:** [minutes] or unlimited
**Attempts:** [N] or unlimited
**Feedback Mode:** immediate/deferred/none

## Learning Objectives ([N] total)

### Remember ([N] LOs)
- LO1: [Description]
- LO2: [Description]

### Understand ([N] LOs)
- LO3: [Description]
- LO4: [Description]

### Apply ([N] LOs)
- LO5: [Description]

### Analyze ([N] LOs)
- LO6: [Description]

### Evaluate ([N] LOs)
- LO7: [Description]

## Distribution Strategy

### By Bloom's Level
| Level | Questions | % | Rationale |
|-------|-----------|---|-----------|
| Remember | [N] | [%] | Foundation |
| Understand | [N] | [%] | Core concepts |
| Apply | [N] | [%] | Application |
| Analyze | [N] | [%] | Higher-order |
| Evaluate | [N] | [%] | Critical |

### By Question Type
| Type | Questions | % | Purpose |
|------|-----------|---|---------|
| MC-Single | [N] | [%] | Versatile assessment |
| MC-Multiple | [N] | [%] | Complex understanding |
| True/False | [N] | [%] | Quick checks |
| Fill-blank | [N] | [%] | Key terms |
| Matching | [N] | [%] | Relationships |

### By Difficulty
| Level | Questions | % | Description |
|-------|-----------|---|-------------|
| Easy | [N] | [%] | Basic recall |
| Medium | [N] | [%] | Application |
| Hard | [N] | [%] | Analysis |

## Question Blueprint

| Q# | LO | Bloom's | Type | Difficulty | Points | Content Focus |
|----|----|---------|----|------------|--------|---------------|
| Q1 | LO1 | Remember | Fill-blank | Easy | 1 | [Description] |
| Q2 | LO1 | Remember | MC-Single | Easy | 1 | [Description] |
| ... | ... | ... | ... | ... | ... | ... |

## Coverage Validation

### By Learning Objective
| LO | Questions | Points | Coverage |
|----|-----------|--------|----------|
| LO1 | [N] | [N] | ✅ Adequate |
| LO2 | [N] | [N] | ✅ Adequate |
| ... | ... | ... | ... |

### Quality Checks
- ✅ All Tier 1 content covered
- ✅ All LOs have minimum 2 questions
- ✅ Bloom's distribution appropriate
- ✅ Question type variety adequate
- ✅ Difficulty progression logical
```

---

## VALIDATION CHECKPOINTS

### After Stage 1: LO Validation
```
Claude confirms:
"Learning Objectives created:
- [N] total LOs
- Bloom's distribution: [breakdown]
- All Tier 1 content covered: [Yes/No]

Missing anything critical?"
```

### After Stage 4: Distribution Check
```
Claude confirms:
"Question distribution:
- Remember: [N] questions ([%])
- Understand: [N] questions ([%])
- Apply: [N] questions ([%])
- Analyze: [N] questions ([%])
- Evaluate: [N] questions ([%])

Does this match your priorities?"
```

### After Stage 7: Final Blueprint Check
```
Claude confirms:
"Complete blueprint:
- [N] questions planned
- All LOs covered (min 2 questions each)
- Distribution validated
- Ready for Question Generation

Approve to proceed?"
```

---

## COMPONENT 2 DECISION POINTS

### Dynamic Decisions (Teacher makes):
1. **Assessment type** (formative vs summative)
2. **Total question count** (based on time/scope)
3. **Bloom's distribution** (% at each level)
4. **Question type mix** (which types to use)
5. **Difficulty distribution** (easy/medium/hard %)

### Static Elements (Framework):
1. **Bloom's taxonomy structure** (6 levels defined)
2. **Question type specifications** (technical codes)
3. **Minimum coverage rules** (2+ questions per LO)
4. **Constructive alignment** (LOs → questions → assessment)

---

## TRANSITION TO COMPONENT 3

**When Assessment Design complete:**

```
Claude provides:
"✅ Assessment Design complete!

Created:
- [N] Learning Objectives (all Tier 1 + Tier 2 covered)
- Question distribution plan
- Assessment strategy defined
- Complete Question Blueprint

Output: Question Blueprint document

Next: Component 3 (Technical Preparation)
- Question type specifications
- Metadata requirements
- Technical constraints validation

OR skip to Component 4 (Question Generation)
- If technical specs already known
- Generate questions directly from blueprint

Which path?"
```

---

## CRITICAL NOTES

**For Claude:**
- Use Content Analysis (Component 1) as foundation
- Propose, don't dictate (teacher makes final decisions)
- Calculate exact question counts after % decided
- Validate minimum coverage (2+ questions per LO)
- Check Tier 1 content fully covered

**For Human:**
- Key decisions: assessment type, distribution, question count
- Bloom's %: Higher Remember/Understand for foundational courses
- Question types: Auto-grading for formative, consider manual for summative
- Blueprint is CONTRACT for Question Generation phase

---

Component 2 creates the strategic plan. Next: Component 3 (Technical Preparation) or Component 4 (Question Generation).
