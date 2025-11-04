# Modular QGen
## Modular Question Generation Framework

**A component-based approach to AI-assisted assessment development**

---

## Framework Identity

**Full Name:** Modular Question Generation Framework  
**Short Name:** Modular QGen  
**Version:** 3.0 - Component Architecture  
**Status:** Production Framework  
**Philosophy:** Teacher-driven, context-adaptive, modular assembly

**Tagline:** *"Build quality questions your way - 6 components, 5 workflows, unlimited flexibility"*

---

## What is Modular QGen?

Modular QGen is a **component-based framework** for generating high-quality assessment questions with AI assistance. Instead of following a rigid linear process, teachers assemble **6 modular components** into **5 proven workflows** that match their starting context.

**Core Innovation:**
- Not "Phase 1 → 2 → 3" (one path for everyone)
- But "6 components you assemble YOUR way" (context-adaptive)

**Key Features:**
- 🔷 **Dynamic components** = Dialogue-driven (teacher decides)
- 🔶 **Static components** = Checklist-driven (follow specs)
- 🔷🔶 **Hybrid components** = Both dialogue and validation
- ⚡ **5-8 hours** for 40-50 quality questions
- 🎯 **Proven in practice** (Evolution case study: 72 questions)

---

## PART 1: FIND YOUR WORKFLOW

### Decision Tree: Where Are You Starting?

```
┌─────────────────────────────────────────────────┐
│  "What's your current situation?"              │
└─────────────────────────────────────────────────┘
                    │
        ┌───────────┼───────────┐
        │           │           │
        ▼           ▼           ▼
        
┌─────────────┐ ┌──────────────┐ ┌─────────────┐
│ MATERIALS   │ │  STANDARDS   │ │ QUESTIONS   │
│  EXIST      │ │   EXIST      │ │   EXIST     │
└─────────────┘ └──────────────┘ └─────────────┘
        │               │               │
        ▼               ▼               ▼
        
"I have teaching    "I must align    "I have questions
 materials"          to curriculum"   that need work"
        │               │               │
        ├───────────────┼───────────────┤
        │               │               │
        ▼               ▼               ▼
        
  WORKFLOW A    WORKFLOW B        WORKFLOW D
Content-Driven  Standards-Driven  Revision-Driven
   (1→2→3→4)      (2→1→3→4)        (1→2→4→3)

        ┌───────────┐
        │  STARTING │
        │ FROM      │
        │ SCRATCH?  │
        └───────────┘
              │
        ┌─────┴─────┐
        ▼           ▼
        
  WORKFLOW C   WORKFLOW E
Question-First Technical-First
   (4→1→2→3)     (3→1→2→4)
```

**All workflows converge on:**
```
→ [Component 5: QA] → [Component 6: Export] → DONE
```

---

### Quick Selector

**Choose the description that matches your situation:**

#### Workflow A: Content-Driven
**"I have recordings, slides, textbook pages, lecture notes"**
- ✅ Teaching materials exist
- ✅ Need to structure content into assessments
- ✅ Questions should reflect actual teaching

**Sequence:** Content Analysis → Assessment Design → Technical Setup → Question Generation → QA → Export

**Example:** Evolution QTI case study (actual implementation!)

---

#### Workflow B: Standards-Driven  
**"I must align to GY25 / curriculum standards / learning outcomes"**
- ✅ Learning objectives predetermined
- ✅ Must demonstrate alignment
- ✅ Content selected to meet standards

**Sequence:** Assessment Design → Content Analysis → Technical Setup → Question Generation → QA → Export

**Example:** New GY25-compliant course from scratch

---

#### Workflow C: Question-First
**"I know what I want to ask, let me start writing questions"**
- ✅ Teaching intuition strong
- ✅ Questions come naturally
- ✅ Formalization can wait

**Sequence:** Question Generation → Content Analysis → Assessment Design → Technical Setup → QA → Export

**Example:** Experienced teacher with clear sense of what matters

---

#### Workflow D: Revision-Driven
**"I have old quizzes/exams that need improvement"**
- ✅ Existing questions available
- ✅ Need systematic improvement
- ✅ May have gaps or misalignments

**Sequence:** Content Analysis (audit) → Assessment Design (gap analysis) → Question Generation (targeted) → Technical Setup → QA → Export

**Example:** Updating last year's exam with new materials

---

#### Workflow E: Technical-First
**"I'm migrating questions to new LMS (Inspera)"**
- ✅ Technical requirements known
- ✅ Must adapt to platform constraints
- ✅ Questions exist but need reformatting

**Sequence:** Technical Setup → Content Analysis → Assessment Design → Question Generation (conversion) → QA → Export

**Example:** Moving from old system to Inspera

---

## PART 2: THE COMPONENTS

### Overview: 6 Modular Building Blocks

| Component | Type | Time | Purpose |
|-----------|------|------|---------|
| **1. Content Analysis** | 🔷 DYNAMIC | 1-2h | Understand what was taught |
| **2. Assessment Design** | 🔷 DYNAMIC | 1-2h | Define what to assess |
| **3. Technical Setup** | 🔶 STATIC | 30min | Configure metadata |
| **4. Question Generation** | 🔷🔶 HYBRID | 2-4h | Create questions |
| **5. Quality Assurance** | 🔷🔶 HYBRID | 1h | Validate quality |
| **6. Export/Integration** | 🔶 STATIC | 30min | Convert & import |

**Legend:**
- 🔷 **DYNAMIC** = Dialogue-driven, teacher makes decisions through conversation
- 🔶 **STATIC** = Checklist-driven, follow specifications exactly
- 🔷🔶 **HYBRID** = Both dialogue (content) and checklist (format) elements

---

### Component 1: Content Analysis 🔷 DYNAMIC

**Type:** Dialogue-driven pedagogical analysis  
**Time:** 1-2 hours  
**When to use:** When you have teaching materials to analyze

#### Entry Points
You can start here if you have:
- Lecture recordings or transcripts
- PowerPoint presentations or PDFs
- Textbook chapters or sections
- Lecture notes or teaching materials
- Student work showing misconceptions

#### What This Component Does
Transforms raw teaching materials into **structured pedagogical knowledge**:
- Extract key concepts and relationships
- Identify teacher emphasis ("detta kommer på provet")
- Document examples used in teaching
- Surface common student misconceptions
- Note practical demonstrations
- Map to curriculum requirements

#### Process: Structured Dialogue

**This is NOT "read these materials and tell me what they say"**  
**This IS "conversation to surface pedagogical knowledge"**

##### Dialogue Pattern 1: Material Inventory

**AI starts:**
```
"What teaching materials do you have for this topic?"
```

**Teacher provides:**
```
"I have 3 lecture recordings, 2 PowerPoint decks, 
and textbook pages 168-217"
```

**AI probes:**
```
"Which of these materials best captures what you 
emphasized in class?"
```

**Teacher indicates priorities:**
```
"Recording 2 has my main explanation of natural selection.
PowerPoint 1 has the examples I use.
Textbook is comprehensive but I don't cover everything."
```

**AI clarifies:**
```
"So: Recording 2 = core concepts
     PowerPoint 1 = key examples  
     Textbook = reference, selective coverage
     
Should I focus analysis there?"
```

**Teacher confirms and adds context:**
```
"Yes. Also, I always emphasize that evolution = 
change in allele frequency - exact wording.
And students always confuse natural selection 
with genetic drift."
```

**AI documents:**
```
✓ Core material: Recording 2
✓ Examples source: PowerPoint 1  
✓ Reference: Textbook (selective)
✓ Must memorize: "Evolution = change in allele frequency"
✓ Common confusion: Selection vs. drift
```

##### Dialogue Pattern 2: Concept Extraction

**AI analyzes materials, then discusses:**

```
"I've identified these major concept clusters:

1. Evolution fundamentals (definition, population, allele)
2. Natural selection mechanism (Darwin's principles)
3. Types of selection (directional, stabilizing, disruptive)
4. Evidence for evolution (fossils, embryology, etc.)
5. Speciation and species concepts

Does this match your teaching structure?"
```

**Teacher evaluates:**
```
"Good, but you're missing:
- Origin of life (chemical evolution)
- Sexual selection (important!)
- And 'types of selection' should include genetic drift
  even though it's not technically selection"
```

**AI adjusts:**
```
"Updated structure:
1. Evolution fundamentals
2. Natural selection mechanism  
3. Selection types + genetic drift
4. Sexual selection
5. Evidence for evolution
6. Speciation
7. Origin of life

Better?"
```

**Teacher confirms:**
```
"Yes, and within natural selection mechanism,
make sure Darwin's THREE principles are clear"
```

##### Dialogue Pattern 3: Example Mapping

**AI identifies examples, asks about pedagogical purpose:**

```
"I see these major examples in your materials:
- Peppered moth (industrial melanism)
- Darwin's finches (Galápagos)
- Human thumb (opposable)
- Antibiotic resistance

How do you use each of these?"
```

**Teacher provides pedagogical context:**
```
"Peppered moth = classic natural selection story
                 (light→dark→light again)
                 
Darwin's finches = speciation example
                    (allopatric, adaptive radiation)
                    
Human thumb = adaptation example
              (tool use, evolutionary advantage)
              
Antibiotic resistance = modern application
                         (connect to real life)"
```

**AI documents example purposes:**
```
✓ Peppered moth → Natural selection + reversibility
✓ Darwin's finches → Speciation mechanism
✓ Human thumb → Adaptation concept
✓ Antibiotic resistance → Contemporary relevance
```

##### Dialogue Pattern 4: Misconception Surfacing

**AI asks explicitly:**
```
"What do students consistently get wrong about evolution?"
```

**Teacher shares teaching experience:**
```
"Every year, students think:
1. Evolution has a direction or goal
2. Organisms choose to evolve
3. Individuals evolve (not populations)
4. Mutation happens BECAUSE it's needed
5. 'Survival of the fittest' = physically strongest"
```

**AI probes deeper:**
```
"For #1 'evolution has direction' - 
what's the root of this misconception?"
```

**Teacher explains:**
```
"They think 'better' means objectively better,
not better FOR CURRENT ENVIRONMENT.
Also language like 'higher organisms' reinforces this."
```

**AI documents for question design:**
```
✓ Misconception: Evolution has direction/goal
  → Root: Confusion about 'better' = context-dependent
  → Address: Emphasize environmental fit, not absolute improvement
  → Example: Blindness in cave fish (loss can be adaptive)
```

##### Dialogue Pattern 5: Emphasis Documentation

**AI asks about assessment priorities:**
```
"You mentioned 'detta kommer på provet' in recording.
What specifically MUST students know?"
```

**Teacher indicates non-negotiables:**
```
"They MUST be able to:
1. Recite exact definition of evolution
2. State Darwin's three principles  
3. Distinguish selection types from scenarios
4. Identify types of evidence

These are minimum competency."
```

**AI documents assessment priorities:**
```
TIER 1 (Essential):
- Evolution definition (exact wording)
- Darwin's three principles (by heart)
- Selection type identification (scenario-based)
- Evidence type recognition

TIER 2 (Important):
- [continues]
```

#### Exit Deliverable

**Document:** `[Topic]_Content_Analysis.md`

**Contains:**
```markdown
# [Topic] Content Analysis for Assessment

## Source Materials
- [List with priorities marked]

## Core Concepts (Hierarchical)
1. [Major concept]
   - [Sub-concept]
   - [Sub-concept]
2. [Major concept]
   ...

## Key Examples (with Pedagogical Purpose)
- [Example] → [What it teaches]
- [Example] → [What it teaches]

## Common Misconceptions (with Roots)
- [Misconception] → [Why it happens] → [How to address]
- [Misconception] → [Why it happens] → [How to address]

## Assessment Priorities
### Tier 1 (Essential):
- [Must know]
### Tier 2 (Important):
- [Should know]
### Tier 3 (Enrichment):
- [Nice to know]

## Curriculum Alignment
- [Requirement] → [Coverage in materials]
- [Requirement] → [Coverage in materials]

## Pedagogical Notes
- [Teaching emphasis]
- [Example quality notes]
- [Over-curriculum content flagged]
```

#### Connections

**Can flow TO:**
- Component 2 (Assessment Design) - most common
- Component 4 (Question Generation) - if LOs already defined

**Can flow FROM:**
- Start (Workflow A: Content-Driven)
- Component 2 (Workflow B: Standards-Driven) - analyze content against LOs
- Component 4 (Workflow C: Question-First) - retrospective analysis

---

### Component 2: Assessment Design 🔷 DYNAMIC

**Type:** Dialogue-driven pedagogical planning  
**Time:** 1-2 hours  
**When to use:** When you need to define learning objectives and structure

#### Entry Points
You can start here if you have:
- Curriculum standards to meet (e.g., GY25)
- Content analysis completed
- Course objectives already defined
- Need to formalize implicit objectives

#### What This Component Does
Transforms content/standards into **assessable learning objectives**:
- Define what students should be able to DO
- Map to Bloom's taxonomy levels
- Plan question distribution
- Determine assessment strategy
- Establish feedback approach

#### Process: Three Connected Dialogues

##### Dialogue 1: Assessment Strategy

**This establishes the PURPOSE and CONSTRAINTS**

**AI opens with context questions:**
```
"Before we design specific objectives, help me understand:

1. What's the PURPOSE of this assessment?
   - Practice and learning (formative)?
   - Evaluation and grading (summative)?
   - Both?

2. How will results be USED?
   - Identify struggling students?
   - Determine grades?
   - Guide further teaching?

3. What are the CONSTRAINTS?
   - Time available?
   - Student level and preparedness?
   - LMS capabilities?
   - Grading resources (auto vs manual)?
"
```

**Teacher provides context:**
```
"This is formative - practice before the real exam.
Students need to identify weak areas.
We have 60 minutes, online via Inspera.
Must be auto-graded (I have 120 students).
They're first-year university, biology majors."
```

**AI explores implications:**
```
"Given formative purpose with auto-grading:

- Should allow multiple attempts?
- Should provide immediate feedback?
- Should include hints/explanations?
- Focus on coverage or mastery?

What's your thinking?"
```

**Teacher decides:**
```
"Unlimited attempts, yes.
Immediate detailed feedback.
Focus on COVERAGE - hit all key concepts.
Feedback should teach, not just confirm."
```

**AI synthesizes strategy:**
```
ASSESSMENT STRATEGY:
────────────────────
Type: Formative (practice)
Purpose: Self-assessment + learning
Attempts: Unlimited
Feedback: Immediate + detailed
Time: 60 minutes → ~40-50 questions
Grading: 100% auto-graded
Focus: Broad coverage of concepts
Level: First-year university

This means:
✓ Questions must be self-grading types only
✓ Rich feedback is essential
✓ Difficulty should span range (easy→medium→hard)
✓ No essay or manual grading questions
✓ Emphasize understanding over memorization

Proceed with this strategy?
```

**Teacher confirms or adjusts:**
```
"Yes, exactly right."
```

##### Dialogue 2: Learning Objectives Development

**This is the CORE pedagogical work**

**AI's role: Question-asker and draft-proposer**  
**Teacher's role: Decision-maker and expertise-provider**

###### Starting Point: Content-Driven

**If coming FROM Content Analysis:**

**AI proposes objectives based on content:**
```
"Based on your content analysis, I'm seeing these
natural objective clusters:

FOUNDATION (Remember/Understand):
- Define evolution scientifically
- Recall key terminology (population, allele, etc.)
- Explain Darwin's three principles
- Describe natural selection process

APPLICATION (Apply):
- Identify selection type from scenarios
- Distinguish selection from genetic drift
- Apply knowledge of sexual selection

ANALYSIS (Analyze):
- Compare different species concepts
- Analyze evidence types
- Evaluate evolutionary explanations

Does this capture your teaching priorities?"
```

**Teacher evaluates:**
```
"Good foundation, but missing:
- Students must CALCULATE allele frequency
  (not just define it)
- 'Apply knowledge of sexual selection' is too vague
- Add: Evaluate common misconceptions"
```

**AI refines:**
```
"Updated:

FOUNDATION:
- LO1: Define evolution as change in allele frequency
- LO2: Calculate allele frequency from genotype data
       [NEW - shifted to Apply level]
- LO3: Recall key terminology...
- LO4: Explain Darwin's three principles
- LO5: Describe natural selection mechanism

APPLICATION:
- LO6: Identify selection type from novel scenarios
- LO7: Distinguish natural selection from genetic drift in examples
- LO8: Differentiate intrasexual from intersexual selection
       [REFINED - more specific]

ANALYSIS:
- LO9: Compare biological vs ecological species concepts
- LO10: Analyze strengths/weaknesses of evidence types
- LO11: Evaluate common misconceptions about evolution
        [NEW - added as you requested]

Better?"
```

**Teacher further refines:**
```
"Yes, but LO2 might be over-curriculum.
Let me check... yes, allele frequency calculation
is not in GY25. Remove it.

Also split LO4 - Darwin's principles should be
its own LO (it's that important), and natural selection
mechanism should be separate."
```

**AI adjusts with rationale:**
```
"Understood. Removing LO2 (allele calculation).

Splitting LO4:
- LO4: State Darwin's three main principles (Remember)
- LO5: Explain how natural selection works (Understand)

This emphasizes importance of Darwin's principles
and allows separate assessment of:
a) Knowing the principles (factual)
b) Understanding the mechanism (conceptual)

Agree?"
```

**Iteration continues until teacher satisfied.**

###### Starting Point: Standards-Driven

**If coming FROM Standards (e.g., GY25):**

**AI starts with curriculum:**
```
"Looking at GY25 Biologi 1, the Centralt innehåll includes:

'Evolutionens mekanismer för livets utveckling,
inklusive variation, nedärvning och naturligt urval'

'Biologisk mångfald'

'Naturvetenskapliga modeller för livets uppkomst'

Let's develop LOs that explicitly address these.

For 'evolutionens mekanismer' - what specifically
should students be able to DO?"
```

**Teacher interprets standards:**
```
"They should be able to:
- Explain each mechanism (variation, heredity, selection)
- Apply mechanism understanding to examples
- Distinguish between different mechanisms"
```

**AI proposes specific LOs:**
```
"From that, I'd suggest:

LO1: Explain how variation arises in populations
LO2: Explain role of heredity in evolution
LO3: Explain how natural selection operates
LO4: Apply understanding of mechanisms to novel scenarios
LO5: Distinguish between selection and drift

These clearly address the standard.
Good coverage?"
```

**Teacher evaluates against curriculum:**
```
"Yes, but GY25 also requires students to use
'modeller och teorier' - so add:

LO6: Evaluate evolution as scientific theory"
```

**AI checks alignment:**
```
"Adding:
LO6: Evaluate strengths of evolution as scientific theory

This addresses GY25's 'Ämnet syfte' requirement:
'kunskaper om biologins modeller och teorier'

✓ Complete GY25 alignment
```

##### Dialogue 3: Distribution Planning

**AI proposes based on strategy + LOs:**

```
"You have 11 learning objectives:
- 3 at Remember level
- 4 at Understand level  
- 2 at Apply level
- 2 at Analyze level

For a 60-minute formative assessment (40-50 questions):

OPTION A: Coverage-focused
- Remember: 12 questions (30%)
- Understand: 16 questions (40%)
- Apply: 8 questions (20%)
- Analyze: 4 questions (10%)
Total: 40 questions

OPTION B: Application-heavy
- Remember: 8 questions (20%)
- Understand: 12 questions (30%)
- Apply: 16 questions (40%)
- Analyze: 4 questions (10%)
Total: 40 questions

Given formative purpose, I'd recommend Option A
(broader coverage, build foundation).

What's your thinking?"
```

**Teacher evaluates:**
```
"Option A, but add more Analyze questions.
Students need practice with higher-order thinking.
Cut some Remember questions."
```

**AI revises:**
```
"Adjusted:
- Remember: 10 questions (24%)
- Understand: 16 questions (38%)
- Apply: 10 questions (24%)
- Analyze: 6 questions (14%)
Total: 42 questions

This:
✓ Reduces basic recall (24% vs 30%)
✓ Increases higher-order (38% vs 20%)
✓ Maintains formative coverage focus
✓ Fits 60-minute timeframe

Point distribution:
- Remember: 1 point each = 10 points
- Understand: 1 point each = 16 points
- Apply: 2 points each = 20 points
- Analyze: 3 points each = 18 points
Total: 64 points

Work for you?"
```

**Teacher confirms:**
```
"Perfect. Let's use this."
```

#### Exit Deliverable

**Document:** `[Topic]_Assessment_Plan.md`

**Contains:**
```markdown
# [Topic] Assessment Plan

## Assessment Strategy
- Type: [Formative/Summative]
- Purpose: [Specific goals]
- Time limit: [X minutes]
- Attempts: [Number or unlimited]
- Feedback: [When and how]
- Grading: [Auto/Manual/Hybrid]

## Learning Objectives

### Remember (X objectives)
- LO1: [Specific, measurable objective]
- LO2: [Specific, measurable objective]

### Understand (X objectives)
- LO3: [Specific, measurable objective]
- LO4: [Specific, measurable objective]

### Apply (X objectives)
- LO5: [Specific, measurable objective]

### Analyze (X objectives)
- LO6: [Specific, measurable objective]

### Evaluate (X objectives)
- LO7: [Specific, measurable objective]

## Question Distribution Plan

| Bloom's Level | # Questions | % | Points Each | Total Points |
|---------------|-------------|---|-------------|--------------|
| Remember      | X           | X%| 1           | X            |
| Understand    | X           | X%| 1           | X            |
| Apply         | X           | X%| 2           | X            |
| Analyze       | X           | X%| 3           | X            |
| Evaluate      | X           | X%| 5           | X            |
| **TOTAL**     | **X**       |100%|            | **X**        |

## LO Coverage Plan

| LO | Description | # Questions | Bloom's | Points |
|----|-------------|-------------|---------|--------|
| LO1| [desc]     | X           | Remember| X      |
| LO2| [desc]     | X           | Understand| X    |
...

## Question Type Strategy

Given [auto-grading requirement / formative purpose]:
- Primary: Multiple choice (single/multiple)
- Secondary: Fill-in-blank, Matching
- For process: Gap match, Inline choice
- Avoid: Text area, Essay (manual grading)

## Curriculum Alignment

[GY25 / Standards mapping]
- [Requirement] → [LO coverage]
- [Requirement] → [LO coverage]
```

#### Connections

**Can flow TO:**
- Component 3 (Technical Setup)
- Component 4 (Question Generation)

**Can flow FROM:**
- Start (Workflow B: Standards-Driven)
- Component 1 (Workflow A: Content-Driven)
- Component 4 (Workflow C: Question-First) - retrospective formalization

---

### Component 3: Technical Setup 🔶 STATIC

**Type:** Checklist-driven configuration  
**Time:** 30 minutes  
**When to use:** When you have LOs defined and need metadata structure

#### Entry Points
You can start here if you have:
- Learning objectives defined
- Assessment strategy decided
- Need to configure LMS metadata
- Migrating to new system

#### What This Component Does
Configures **technical metadata** for LMS compliance:
- Create YAML frontmatter structure
- Set language codes correctly
- Configure assessment parameters
- Define searchable labels
- Map question type codes

#### Process: Follow Specifications Exactly

**This is NOT dialogue - this is COMPLIANCE**

##### Step 1: Understand Inspera Label System

**AI explains (once):**
```
In Inspera, "labels" are searchable tags that appear in the question bank.

What becomes searchable:
✓ Course code (e.g., "BIOG001X")
✓ Topic keywords (e.g., "evolution")
✓ Bloom's levels (e.g., "Remember")
✓ LO IDs (e.g., "LO1", "LO2")
✓ Status (e.g., "ready", "review")

Label format rules:
✓ Short (1-3 words)
✓ No prefixes ("LO1" NOT "LO:LO1")
✓ Consistent casing
✓ Plain text only

Questions?
```

**Teacher confirms understanding or asks questions.**

##### Step 2: Checklist - Required Metadata Fields

**AI provides checklist, teacher fills:**

```
REQUIRED FIELDS CHECKLIST:

[ ] test_metadata.title
    Format: Descriptive string
    Your value: ________________

[ ] test_metadata.identifier
    Format: COURSE_TOPIC_VERSION (unique)
    Your value: ________________
    
[ ] test_metadata.language
    Format: ISO 639-1 code (en, sv, no, da)
    Your value: ________________
    
[ ] test_metadata.subject
    Format: Course code (becomes label)
    Your value: ________________
    
[ ] learning_objectives
    Format: Array of {id, description}
    Count: [X objectives from your plan]
    Ready: [Yes/No]
    
[ ] assessment_configuration.type
    Format: "formative" or "summative"
    Your value: ________________
    
[ ] assessment_configuration.feedback_mode
    Format: "immediate", "deferred", or "none"
    Your value: ________________
```

##### Step 3: Generate Valid YAML

**AI generates based on specifications:**

```yaml
---
test_metadata:
  title: "Evolution - Practice Quiz for Biologi 1"
  identifier: "BIOL1_EVOL_GY25_v1"
  language: "sv"
  subject: "BIOG001X"
  author: "Niklas Wahlgren"
  description: "Formativ bedömning av evolutionsmekanismer enligt GY25"
  created_date: "2025-11-02"

assessment_configuration:
  type: "formative"
  time_limit: null
  shuffle_questions: true
  shuffle_choices: true
  feedback_mode: "immediate"
  attempts_allowed: unlimited

learning_objectives:
  - id: "LO1"
    description: "Define evolution as change in allele frequency"
  - id: "LO2"
    description: "Explain Darwin's three main principles"
  - id: "LO3"
    description: "Describe how natural selection operates"
  - id: "LO4"
    description: "Identify selection type from novel scenarios"
  - id: "LO5"
    description: "Distinguish natural selection from genetic drift"
  - id: "LO6"
    description: "Analyze types of evidence for evolution"
  - id: "LO7"
    description: "Evaluate common misconceptions about evolution"
---
```

##### Step 4: Validation Checklist

**AI validates automatically:**

```
VALIDATION RESULTS:

✅ test_metadata section present
✅ title is string
✅ identifier is string (unique)
✅ language is ISO 639-1: "sv" ✓
✅ learning_objectives is array
✅ Each LO has 'id' and 'description'
✅ No inline LO format (old style)
✅ All LO IDs follow pattern: LOX

VALIDATION PASSED - Ready for use
```

##### Step 5: Question Type Mapping

**AI provides mapping table:**

```
QUESTION TYPE CODES (for Component 4):

Your Assessment Plan says:
"Primary: Multiple choice, Secondary: Fill-in-blank, Matching"

Use these EXACT codes in questions:

| Type You Want | Inspera Code | Status | Template § |
|---------------|--------------|--------|------------|
| MC-Single | multiple_choice_single | ✅ Production | §1 |
| MC-Multiple | multiple_response | ✅ Production | §2 |
| Fill-blank | fill_blank | ✅ Production | §4 |
| Matching | matching | ✅ Production | §5 |
| True/False | true_false | ✅ Production | §3 |

DO NOT USE other codes - stick to plan.
```

#### Exit Deliverable

**File:** `[Topic]_Metadata.yaml` (ready to insert as frontmatter)

**Plus reference card:**
```
QUICK REFERENCE for Question Generation:

Required in each question:
- Type: [one of the codes above]
- Identifier: [unique per question]
- Points: [integer]
- Learning Objectives: [LO1, LO2, etc.]
- Bloom's Level: [exact spelling: Remember, Understand, Apply, Analyze, Evaluate, Create]

Bloom's Spelling (EXACT):
✓ Remember (NOT Remembering)
✓ Understand (NOT Understanding)
✓ Apply (NOT Applying)
✓ Analyze (NOT Analyzing)
✓ Evaluate (NOT Evaluating)
✓ Create (NOT Creating)
```

#### Connections

**Can flow TO:**
- Component 4 (Question Generation)

**Can flow FROM:**
- Component 2 (most common)
- Component 1 (if LOs implicit in content)

---

### Component 4: Question Generation 🔷🔶 HYBRID

**Type:** Dialogue (content) + Checklist (format)  
**Time:** 2-4 hours  
**When to use:** When ready to create actual questions

#### Entry Points
You can start here if:
- Assessment plan exists (LOs, distribution)
- Technical metadata ready
- OR jumping in exploratory (Workflow C)

#### What This Component Does
Creates **complete, pedagogically sound questions** with:
- Content aligned to LOs
- Plausible distractors
- Educational feedback
- Proper technical format

#### Process: Iterative Dialogue + Technical Validation

**For EACH question:**
```
1. DIALOGUE: Generate content (AI proposes → Teacher evaluates → Iterate)
2. CHECKLIST: Validate format (automated)
3. DECISION: Approve or refine
4. REPEAT for next question
```

**DO NOT batch-generate all questions at once!**

##### Pattern: One Question at a Time

###### Step 1: Contextualize (DIALOGUE)

**AI asks about this specific question:**

```
"Let's work on Question #[X].

From your plan:
- Tests: [LOX] - [description]
- Bloom's: [level]
- Type: [question_type]
- Points: [X]

Before I draft, tell me:
1. What specific aspect of [LOX] should this test?
2. Any particular examples to use/avoid?
3. Common mistakes students make here?
"
```

**Teacher provides context:**

```
"This should test whether they can identify
directional selection from a scenario.

Use a NEW organism (not peppered moth or finches).
Common mistake: confusing directional with disruptive.

Students at this level need clear selection pressure
stated in the scenario."
```

###### Step 2: Draft Generation (DIALOGUE)

**AI generates initial draft:**

```markdown
# Question 15: Selection Type Identification

**Type**: multiple_choice_single
**Identifier**: EVOL_Q015
**Points**: 2
**Learning Objectives**: LO4
**Bloom's Level**: Apply

## Question Text

A population of coastal mice shows variation in fur color, 
ranging from light tan to dark brown. Over several generations, 
a new predatory owl species colonizes the area. These owls hunt 
primarily at night and are very effective at spotting mice against 
the light-colored sand. 

After 20 generations, researchers find that the proportion of 
light-colored mice has significantly decreased, while dark brown 
mice have become much more common. Medium-colored mice remain 
at about the same frequency.

Which type of selection is operating in this population?

## Options

A. Stabilizing selection
B. Directional selection
C. Disruptive selection
D. Sexual selection

## Answer

B

## Feedback

### Correct Response Feedback
Correct! This is directional selection. The environment (owl predation) 
consistently favors ONE extreme (dark brown) over the other (light tan). 
The population mean shifts in one direction - toward darker fur color. 
This is the hallmark of directional selection.

### Incorrect Response Feedback
Think about what's being favored: Is it the extremes (disruptive)? 
The middle (stabilizing)? Or one particular direction (directional)? 
Look at which variant is increasing over time.

### Option-Specific Feedback
- **A**: Stabilizing selection favors the MIDDLE and reduces variation. 
  Here, we see the population shifting toward one extreme (dark), not 
  maintaining the middle.
  
- **B**: Correct! One extreme (dark) is favored, shifting the population 
  mean in that direction.
  
- **C**: Disruptive selection favors BOTH extremes over the middle. Here, 
  only ONE extreme (dark) is favored - light-colored mice are selected 
  against.
  
- **D**: Sexual selection involves mate choice or competition for mates. 
  This scenario is about predation survival, not reproduction.
```

###### Step 3: Teacher Evaluation (DIALOGUE)

**Teacher reviews and provides feedback:**

```
"Good scenario! Novel organism ✓
Clear selection pressure ✓
Directional selection correct ✓

But issues:
1. Option D (sexual selection) is too obviously wrong - 
   no mention of mates at all. Make it more plausible.
   
2. Feedback for C should mention that disruptive would 
   show BOTH light AND dark increasing, not just dark.
   
3. The correct feedback could emphasize the KEY feature:
   population mean SHIFTS in one direction."
```

###### Step 4: Refinement (DIALOGUE)

**AI revises based on feedback:**

```
"Revised:

Option D changed to:
D. Frequency-dependent selection

Option-specific feedback D:
**D**: Frequency-dependent selection occurs when fitness depends 
on how common a trait is in the population. Here, dark fur is 
favored regardless of frequency - it's always advantageous against 
light sand with owl predation.

Option-specific feedback C revised:
**C**: Disruptive selection favors BOTH extremes. We'd see both 
light (perhaps where sand is lighter) AND dark (where sand is 
darker or vegetation is darker) increasing, with medium declining. 
Here, only dark is increasing.

Correct feedback enhanced:
Correct! This is directional selection. The key feature: the 
population MEAN SHIFTS in one direction - toward darker fur. 
One extreme (dark) has consistent advantage, the other extreme 
(light) has consistent disadvantage. The entire distribution 
moves directionally.

Better?"
```

**Teacher:**

```
"Perfect. Approve this question."
```

###### Step 5: Technical Validation (CHECKLIST)

**AI validates format automatically:**

```
TECHNICAL VALIDATION - Q015:

✅ Type: "multiple_choice_single" (valid code)
✅ Identifier: "EVOL_Q015" (unique)
✅ Points: 2 (positive integer)
✅ Learning Objectives: "LO4" (exists in metadata)
✅ Bloom's Level: "Apply" (exact spelling)
✅ Markdown format: Valid
✅ Answer specified: "B"
✅ All options present: A, B, C, D
✅ Feedback sections complete

VALIDATION PASSED ✓
```

###### Step 6: Document and Move On

```
✅ Q015 complete and validated
   
Progress: 15/42 questions (36%)
Remaining: 27 questions
Estimated time: 2.5 hours

Ready for Q016?
```

##### Special Case: Exploratory Generation (Workflow C)

**If starting WITHOUT formal plan:**

**AI asks first:**
```
"You want to start writing questions without a formal plan.
That's fine - we'll discover structure as we go.

What topic are you teaching?
What do you want to ask about first?"
```

**Teacher responds:**
```
"Evolution. I want to ask about natural selection mechanism."
```

**AI generates exploratory question:**
```
[Generates question]

"This question seems to be testing:
- Understanding of natural selection (Understand level)
- Concept: Environmental selection pressure

Should this be a learning objective?
LO?: Explain how natural selection operates"
```

**Teacher:**
```
"Yes, make that LO1."
```

**AI documents as you go:**
```
✓ LO1 created: Explain how natural selection operates
✓ Q001 created testing LO1

Continue with another natural selection question,
or move to different concept?"
```

**Pattern continues:** Questions → Implicit LOs emerge → Formalize later

#### Exit Deliverable

**File:** `[Topic]_Question_Bank.md`

**Contains:**
```markdown
[YAML frontmatter from Component 3]

---

# QUESTIONS

## Section 1: Foundation (Remember/Understand)

# Question 1: [Title]

**Type**: [type_code]
**Identifier**: [UNIQUE_ID]
**Points**: [X]
**Learning Objectives**: [LO1]
**Bloom's Level**: [Level]

## Question Text
[Content]

## Options
[If applicable]

## Answer
[Answer]

## Feedback
[Complete feedback]

---

# Question 2: [Title]
[Continues...]

---

## Section 2: Application (Apply/Analyze)
[Continues...]

---

## Section 3: Mastery (Analyze/Evaluate)
[Continues...]
```

#### Connections

**Can flow TO:**
- Component 5 (Quality Assurance)

**Can flow FROM:**
- Component 3 (most common - after metadata ready)
- Start (Workflow C - exploratory)
- Component 2 (if skipping technical setup temporarily)

---

### Component 5: Quality Assurance 🔷🔶 HYBRID

**Type:** Automated validation + Judgment dialogue  
**Time:** 1 hour  
**When to use:** When question bank is complete (before export)

#### Entry Points
You arrive here when:
- All questions generated
- Ready for systematic validation
- Before committing to export

#### What This Component Does
**Dual validation:**
1. **Technical** - Automated checks (STATIC)
2. **Quality** - Judgment dialogues (DYNAMIC)

#### Process: Two-Stage Validation

##### Stage 1: Technical Validation (STATIC/AUTOMATED)

**AI runs automated checks:**

```
TECHNICAL VALIDATION REPORT

✅ YAML Frontmatter:
   ✓ test_metadata section present
   ✓ All required fields complete
   ✓ Language code valid (sv)
   ✓ learning_objectives is array
   ✓ All LOs have id + description

✅ Per-Question Metadata:
   ✓ All 42 identifiers unique
   ✓ All type codes valid
   ✓ All points positive integers
   ✓ All LO references exist

⚠️ Bloom's Spelling:
   ✓ 40 questions correct
   ✗ Q023: "Analyzing" should be "Analyze"
   ✗ Q031: "Understanding" should be "Understand"

✅ Markdown Format:
   ✓ All questions valid markdown
   ✓ All sections present
   ✓ Proper separator usage

ISSUES FOUND: 2 (Bloom's spelling)
FIX REQUIRED before proceeding
```

**Teacher fixes issues:**
```
"Fixed Q023 and Q031 spellings."
```

**AI re-validates:**
```
✅ ALL TECHNICAL CHECKS PASSED
Ready for Stage 2 (Quality Review)
```

##### Stage 2: Quality Review (DYNAMIC/DIALOGUE)

###### Review 1: Coverage Analysis

**AI analyzes, then discusses:**

```
LEARNING OBJECTIVE COVERAGE:

| LO | Description | Questions | Count | Status |
|----|-------------|-----------|-------|--------|
| LO1 | Define evolution | Q001, Q002, Q015 | 3 | ✅ Good |
| LO2 | Darwin's principles | Q003, Q004 | 2 | ✅ Good |
| LO3 | Natural selection | Q005-Q010 | 6 | ✅ Good |
| LO4 | Selection types | Q011, Q012, Q015 | 3 | ✅ Good |
| LO5 | Selection vs drift | Q013 | 1 | ⚠️ Low |
| LO6 | Evidence | Q014 | 1 | ⚠️ Low |
| LO7 | Misconceptions | Q016-Q018 | 3 | ✅ Good |

ISSUES:
- LO5: Only 1 question (minimum 2 recommended)
- LO6: Only 1 question (minimum 2 recommended)

RECOMMENDATION:
Add 1 question for LO5 and 1 for LO6.

Your decision?"
```

**Teacher evaluates:**

```
"LO5 (selection vs drift) is important - add one more.
LO6 (evidence) - actually, I cover this heavily in lecture.
One question is enough for formative assessment.

So: Add 1 for LO5, keep LO6 as is."
```

**AI confirms:**
```
"Understood. I'll help generate 1 additional question for LO5.
[Returns to Component 4 dialogue for one question]
Then we'll continue QA review."
```

###### Review 2: Bloom's Distribution

**AI compares actual to plan:**

```
BLOOM'S DISTRIBUTION

Planned vs Actual:

| Level | Planned | Actual | Diff | Status |
|-------|---------|--------|------|--------|
| Remember | 10 (24%) | 11 (26%) | +1 | ✅ Close |
| Understand | 16 (38%) | 15 (36%) | -1 | ✅ Close |
| Apply | 10 (24%) | 11 (26%) | +1 | ✅ Close |
| Analyze | 6 (14%) | 5 (12%) | -1 | ✅ Close |
| TOTAL | 42 | 42 | 0 | ✅ |

ASSESSMENT:
Distribution closely matches plan.
All levels within acceptable variance (±2 questions).

No action required.
```

###### Review 3: Question Type Variety

**AI analyzes and suggests:**

```
QUESTION TYPE DISTRIBUTION

| Type | Count | % | Assessment |
|------|-------|---|------------|
| multiple_choice_single | 30 | 71% | ⚠️ High |
| multiple_response | 4 | 10% | ✅ Good |
| fill_blank | 4 | 10% | ✅ Good |
| matching | 2 | 5% | ✅ Good |
| true_false | 2 | 5% | ✅ Good |

ISSUE:
71% MC-Single can be monotonous for students.

SUGGESTION:
Convert 3-4 related MC-Single questions to:
- 1 Matching question (combines related items)
- 2-3 Fill-blank (for key term recall)

This would reduce MC-Single to ~60% and increase variety.

Want to make these changes?"
```

**Teacher decides:**

```
"Good point. Let's convert:
- Q003, Q004, Q005 (Darwin's principles) → 1 Matching
- Q001 and Q002 (definitions) → Fill-blank

That gives us better variety without losing content."
```

**AI implements:**
```
"I'll help redesign those questions.
[Returns to Component 4 for revisions]"
```

###### Review 4: Alignment Spot-Check

**AI samples questions for alignment:**

```
ALIGNMENT VALIDATION (Sample: 10 random questions)

✅ Q001: Correctly tests LO1 at Remember level
✅ Q005: Correctly tests LO3 at Understand level
✅ Q011: Correctly tests LO4 at Apply level
⚠️ Q023: Claims "Understand" but actually tests "Apply"
✅ Q030: Correctly tests LO6 at Analyze level
...

MISALIGNMENT IDENTIFIED:

Q023: Selection Type Application
- Claims: LO3 (Natural selection), Bloom's = Understand
- Actual: Asks to identify selection type in scenario
- Real Bloom's: Apply (not Understand)
- Real LO: Should be LO4 (selection types)

FIX: Change metadata to LO4, Apply

Agree?"
```

**Teacher:**
```
"Yes, you're right. Change Q023 metadata."
```

###### Review 5: Feedback Quality Spot-Check

**AI samples feedback quality:**

```
FEEDBACK QUALITY CHECK (Sample: 5 questions)

✅ Q005: Correct feedback explains mechanism + references lecture
✅ Q011: Option-specific feedback addresses each misconception
⚠️ Q018: Correct feedback just says "Correct!" - no explanation
✅ Q025: Incorrect feedback guides to understanding
✅ Q030: Feedback connects to other concepts

ISSUE:
Q018 has minimal feedback.

CURRENT:
"Correct! That's the right answer."

RECOMMENDED:
"Correct! [Brief explanation of WHY this is right and 
how it connects to the concept]"

Want to enhance Q018 feedback?"
```

**Teacher:**
```
"Yes, let's improve Q018 feedback."
```

##### Final Sign-Off

**After all issues addressed:**

```
QUALITY ASSURANCE COMPLETE

✅ Technical validation: PASSED
✅ Coverage analysis: RESOLVED
✅ Bloom's distribution: VALIDATED
✅ Type variety: IMPROVED
✅ Alignment: CORRECTED
✅ Feedback quality: ENHANCED

READY FOR EXPORT

Question Bank Status: PRODUCTION-READY ✓
```

#### Exit Deliverable

**Document:** `[Topic]_QA_Report.md`

**Plus:** Updated question bank with all fixes applied

#### Connections

**Can flow TO:**
- Component 6 (Export/Integration) - ONLY after passing QA

**Can flow FROM:**
- Component 4 (Question Generation complete)

**May loop back to:**
- Component 4 (if significant gaps or issues found)

---

### Component 6: Export/Integration 🔶 STATIC

**Type:** Procedural/Checklist  
**Time:** 30 minutes  
**When to use:** After QA passed - ready to import to LMS

#### Entry Points
You arrive here when:
- QA complete and passed
- Question bank production-ready
- Need to import to Inspera

#### What This Component Does
**Convert and import:**
- Markdown → QTI XML
- Package for Inspera
- Import and verify
- Test functionality

#### Process: Follow Procedure Exactly

##### Step 1: Pre-Export Checklist

```
PRE-EXPORT CHECKLIST:

[ ] QA report shows "PRODUCTION-READY"
[ ] All validation issues resolved
[ ] Question bank markdown file saved
[ ] Backup created
[ ] Ready to proceed

Confirm all items checked.
```

##### Step 2: QTI Conversion

**Option A: Automated Script**
```bash
python modular_qgen_converter.py \
  --input "[Topic]_Question_Bank.md" \
  --output "generated/" \
  --validate
```

**Option B: Manual Process**
```
Follow Inspera import wizard:
1. Export questions one section at a time
2. Use Inspera's QTI import
3. Verify each batch before proceeding
```

##### Step 3: Package Validation

```
PACKAGE VALIDATION CHECKLIST:

[ ] All XML files generated
[ ] imsmanifest.xml present
[ ] No XML syntax errors
[ ] UTF-8 encoding verified
[ ] File count matches question count
[ ] ZIP package created successfully

All checks passed: [Yes/No]
```

##### Step 4: Inspera Import

**Procedure:**
```
1. Login to Inspera
2. Navigate to Question Bank
3. Select import folder
4. Choose "Import QTI Package"
5. Upload ZIP file
6. Wait for processing
7. Review import log
8. Verify question count
9. Spot-check 3-5 questions
```

**Import Verification:**
```
[ ] All questions imported (count matches)
[ ] No error messages in log
[ ] Labels visible and correct
[ ] Random sample renders correctly
[ ] Feedback displays properly
[ ] Images load (if applicable)
[ ] Math renders (if applicable)
```

##### Step 5: Functionality Test

**Create test assessment:**
```
1. Add 5-10 representative questions
2. Include variety of types
3. Preview as student
4. Answer some correctly, some incorrectly
5. Verify:
   [ ] Auto-grading works
   [ ] Feedback displays correctly
   [ ] Navigation functions
   [ ] Point calculations correct
   [ ] All question types render properly
```

##### Step 6: Documentation

**Create implementation record:**

```markdown
# [Topic] - Implementation Record

**Date Imported:** [YYYY-MM-DD]
**Inspera Location:** [Folder path]
**Package:** [filename.zip]
**Questions:** [X total]
**Total Points:** [X]

## Import Status
✅ Successful
- Errors: None
- Warnings: [if any]

## Testing
✅ Preview completed
✅ Auto-grading verified
✅ Feedback functional
✅ All question types working

## Access
- Search labels: [list]
- Folder: [path]
- Contact: [email]

## Notes
[Any observations or future improvements]
```

#### Exit Deliverable

**Deliverables:**
1. `[Topic]_QTI_Package.zip` (imported)
2. `[Topic]_Implementation_Record.md`
3. Questions live in Inspera
4. Test assessment created and verified

**Status:** READY FOR USE WITH STUDENTS

#### Connections

**Can flow TO:**
- Done! (Question bank ready for use)
- Future: Component 1 or 4 (for updates/improvements)

**Can ONLY flow FROM:**
- Component 5 (QA passed)

---

## PART 3: WORKFLOW PATTERNS

[Complete workflow examples for A, B, C, D, E - same content as before but under "Modular QGen" branding]

### Workflow A: Content-Driven 
**"I have teaching materials to analyze"**

**Sequence:** 1 → 2 → 3 → 4 → 5 → 6

**Real Example: Evolution QTI (Modular QGen in Action)**

This is the actual workflow used with Modular QGen:

```
Component 1: Content Analysis
→ Evolution_Innehållsanalys_för_Testplanering.md
   
Component 2: Assessment Design  
→ Evolution_Testplan_Steg1_UPPDATERAD.md
   
Component 3: Technical Setup
→ inspera_metadata_generator.py + lo_config.yaml
   
Component 4: Question Generation
→ Evolution_Complete_72_Questions_FINAL.md
   
Component 5: Quality Assurance
→ Fragor_Typrekommendationer_Analys.md
   
Component 6: Export/Integration
→ Ready for QTI conversion
```

**Result:** 72 high-quality questions in ~5-8 hours (vs 24+ hours without framework)

[Continue with other workflow examples...]

---

## PART 4: QUICK REFERENCE

### Framework Overview

**Name:** Modular QGen (Modular Question Generation Framework)

**Purpose:** Generate high-quality assessment questions with AI assistance

**Method:** Component-based assembly with flexible workflows

### The 6 Components

| # | Component | Type | Time |
|---|-----------|------|------|
| 1 | Content Analysis | 🔷 DYNAMIC | 1-2h |
| 2 | Assessment Design | 🔷 DYNAMIC | 1-2h |
| 3 | Technical Setup | 🔶 STATIC | 30min |
| 4 | Question Generation | 🔷🔶 HYBRID | 2-4h |
| 5 | Quality Assurance | 🔷🔶 HYBRID | 1h |
| 6 | Export/Integration | 🔶 STATIC | 30min |

### The 5 Workflows

| Workflow | Start | Use When |
|----------|-------|----------|
| A: Content-Driven | Component 1 | Have teaching materials |
| B: Standards-Driven | Component 2 | Must align to curriculum |
| C: Question-First | Component 4 | Want to start writing |
| D: Revision-Driven | Component 1 | Improving old questions |
| E: Technical-First | Component 3 | Migrating to new LMS |

### Time Investment

**Total:** 5-8 hours for 40-50 questions
**Breakdown:**
- Planning (Components 1-3): 2-3 hours
- Generation (Component 4): 2-4 hours
- Quality (Components 5-6): 1-2 hours

### Success Indicators

You're using Modular QGen successfully when:

✅ Process feels natural, not forced  
✅ Teacher drives decisions, AI executes  
✅ Components connect logically  
✅ Quality meets standards  
✅ Time investment reasonable  
✅ Would use again

---

## GETTING STARTED

### Quick Start (15 Minutes)

1. **Identify your situation** → Use decision tree
2. **Pick your workflow** → A, B, C, D, or E
3. **Read that workflow example** → See it in action
4. **Start your first component** → Follow dialogue/checklist pattern
5. **Build iteratively** → One component at a time

### Remember

**🔷 DYNAMIC = Conversation**
- You decide, AI proposes
- Iterate until satisfied
- Quality through dialogue

**🔶 STATIC = Compliance**
- Follow specifications
- Validate automatically
- Technical accuracy

### Getting Help

**Stuck? Review:**
- Decision tree (Part 1)
- Component details (Part 2)
- Workflow examples (Part 3)
- This quick reference (Part 4)

---

## ABOUT MODULAR QGEN

### Development

**Created:** 2025  
**Proven:** Evolution case study (72 questions)  
**Status:** Production framework

### Philosophy

**Teacher-Centered:**
- Teacher expertise drives quality
- AI handles execution and scale
- Teacher always in charge

**Context-Adaptive:**
- Multiple entry points
- Flexible workflows
- Your way, not one way

**Quality-Focused:**
- Systematic validation
- Iterative refinement
- Production-ready output

### Citation

**If using Modular QGen in academic work:**

```
Modular QGen: Modular Question Generation Framework (2025)
A component-based approach to AI-assisted assessment development.
```

---

## FINAL NOTE

**Modular QGen is your framework.**

- Choose YOUR starting point
- Follow YOUR workflow
- Build YOUR way
- Achieve YOUR quality

**The 6 components work together, however YOU arrange them.**

**Start where it makes sense. Build what you need. Maintain your standards.**

---

**Framework:** Modular QGen v3.0  
**Documentation Updated:** November 2025  
**Status:** Production Ready  
**License:** Open Educational Framework
