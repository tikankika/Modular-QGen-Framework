# COMPONENT 4: QUESTION GENERATION

## Three-Stage Question Development Process

**Type:** 🔷🔶 HYBRID (Dynamic + Static)  
**Output:** Complete question bank (QTI-ready)  
**Purpose:** Generate questions efficiently with validation checkpoints

---

## WHAT THIS COMPONENT DOES

Creates questions in three stages:
1. **Basic generation** - Question + detailed answer + tags
2. **Distribution validation** - Review coverage before formatting  
3. **Finalization** - Add question types + complete formatting

This prevents wasting time on technical formatting before pedagogical content is validated.

---

## THE THREE STAGES

### **STAGE 4A: BASIC QUESTION GENERATION**

**Claude generates ALL questions in simplified format:**

```markdown
# Question 15: Darwin's principles

**Bloom's Level:** Understand  
**Suggested Tags:** Darwin, principles, natural-selection, core-concept  
**Difficulty:** Medium

## Question
Vilka är Darwins tre principer för naturligt urval?

## Detailed Answer
1. Ärftlig variation finns i populationen
2. Överproduktion och konkurrens om resurser  
3. Naturligt urval - gynnsamma egenskaper blir vanligare

Förklaring: Darwin identifierade att dessa tre faktorer 
tillsammans leder till evolution genom naturligt urval. 
Ärftlig variation ger råmaterial, överproduktion skapar 
konkurrens, och naturligt urval avgör vilka egenskaper 
som sprids i populationen över tid.

## Source
Campus Biologi s. 287-289
```

**What Claude does:**
- Writes question text
- Provides detailed, pedagogical answer
- Suggests tags (LO, concepts, topics)
- Assigns Bloom's level
- Assigns difficulty
- Cites source material

**What Claude does NOT do yet:**
- Choose question type
- Format options A/B/C/D
- Write feedback variations
- Create QTI structure

---

### **STAGE 4B: DISTRIBUTION REVIEW DIALOGUE**

**After ALL questions generated, Claude presents distribution analysis:**

```
✅ All 60 questions generated!

LEARNING OBJECTIVE COVERAGE:
- LO1 (Evolution definition): 4 questions ✅
- LO2 (Darwin's principles): 5 questions ✅
- LO3 (Natural selection): 8 questions ✅
- LO4 (Evidence for evolution): 1 question ⚠️
- LO5 (Speciation): 6 questions ✅
...

BLOOM'S LEVEL DISTRIBUTION:
- Remember: 12 (20%) - Target: 20% ✅
- Understand: 28 (47%) - Target: 45% ✅
- Apply: 15 (25%) - Target: 25% ✅
- Analyze: 5 (8%) - Target: 10% ⚠️

DIFFICULTY DISTRIBUTION:
- Easy: 20 (33%) - Target: 33% ✅
- Medium: 25 (42%) - Target: 42% ✅
- Hard: 15 (25%) - Target: 25% ✅

ISSUES IDENTIFIED:
⚠️ LO4 only has 1 question (target: 2+)
⚠️ "Analyze" level below target (8% vs 10%)
✅ Everything else within targets

What would you like to do?
A) Add questions to address gaps
B) Proceed to finalization  
C) Review specific questions first
```

**Teacher decides:**
- Accept distribution as-is
- Add questions for underrepresented LOs/levels
- Remove questions from overrepresented areas
- Adjust specific questions

**Validation checkpoint:**  
Distribution approved → Proceed to Stage 4C

---

### **STAGE 4C: QUESTION FINALIZATION**

**Claude converts basic questions to complete QTI format:**

For each question, Claude:

**1. Assigns question type**
```
Question 15: "Vilka är Darwins tre principer?"
→ Type: multiple_choice_single (obvious fit)

Question 20: "Explain fitness scenario"
→ Type: multiple_choice_single or extended_text?
→ If ambiguous, Claude asks teacher
```

**2. Creates formatted options** (if applicable)
```markdown
## Options
A. Mutation, drift, och migration
B. Ärftlig variation, överproduktion, och naturligt urval [CORRECT]
C. Adaptation, spekulation, och evolution  
D. Konkurrens, samarbete, och symbios
```

**3. Writes feedback**
```markdown
## Feedback
### Correct
Exakt! Darwin identifierade att ärftlig variation, 
överproduktion, och naturligt urval tillsammans driver 
evolutionära förändringar. Se Campus Biologi s. 287-289.

### Incorrect
Nej, dessa är inte Darwins tre grundprinciper. 
Läs om naturligt urval på s. 287-289 i Campus Biologi.

### Option A
Mutation, drift och migration är evolutionsmekanismer, 
men inte Darwins tre originalprinciper.

### Option C  
Detta är resultat av urval, inte principerna själva.

### Option D
Detta beskriver ekologiska interaktioner, inte urvalsmekanismer.
```

**4. Adds metadata**
```yaml
identifier: EVOL-Q015
type: multiple_choice_single
points: 2
learning_objectives: [LO2]
labels: [Darwin, principles, natural-selection, core-concept]
bloom_level: Understand
difficulty: Medium
source: Campus Biologi s. 287-289
```

---

## OUTPUT STRUCTURE

### **After Stage 4A:**
60 basic questions ready for distribution review

### **After Stage 4B:**  
Distribution validated (possibly 60→72 after adjustments)

### **After Stage 4C:**
Complete question bank in QTI-ready format:
```
evolution_quiz_complete.md
├─ Q1-Q12: Remember level
├─ Q13-Q40: Understand level
├─ Q41-Q55: Apply level  
└─ Q56-Q72: Analyze level
```

---

## VALIDATION CHECKPOINTS

### **After Stage 4A:**
- [ ] All Blueprint questions generated
- [ ] Each has detailed answer
- [ ] Tags assigned
- [ ] Bloom's + difficulty assigned

### **After Stage 4B:**
- [ ] LO coverage acceptable (all LOs have 2+ questions)
- [ ] Bloom's distribution within targets
- [ ] Difficulty distribution within targets
- [ ] Teacher approves proceeding to finalization

### **After Stage 4C:**
- [ ] All questions have assigned types
- [ ] Options created (where applicable)
- [ ] Feedback complete
- [ ] Metadata complete
- [ ] QTI format validated

---

## DIALOGUE PRINCIPLES

### **Stage 4A: Claude should**
- Generate questions independently based on Blueprint
- Use Content Analysis insights for scenarios/examples
- Cite specific sources from teaching materials
- Write detailed answers (teaching material, not test key)

### **Stage 4B: Claude should**
- Present complete distribution analysis
- Identify gaps clearly
- Recommend specific adjustments if needed
- Wait for teacher approval before proceeding

### **Stage 4C: Claude should**
- Assign obvious question types automatically
- Ask about ambiguous cases
- Generate plausible distractors
- Write pedagogical feedback (not just correct/incorrect)

### **Teacher provides:**
- Approval to proceed after distribution review
- Decisions on ambiguous question types
- Guidance on distractor quality if needed

---

## TRANSITION TO COMPONENT 5

**When complete:**
```
✅ 72 questions finalized
✅ All metadata assigned
✅ QTI format validated

Next: Component 5 (Quality Assurance)
- Pedagogical review
- Technical validation
- Distractor quality check
```

---

## NOTES ON FLEXIBILITY

**Question types can be chosen earlier:**
- If obvious from Blueprint (e.g., "Match X to Y" → matching)
- If teacher specifies in Component 2
- If consistent pattern (e.g., all Remember = fill_blank)

**In these cases:**
- Stage 4A generates with types already
- Stage 4C becomes faster (just add feedback + metadata)

**But default workflow:**
- Stage 4A: Content first
- Stage 4B: Validate distribution  
- Stage 4C: Add technical formatting

This allows maximum flexibility for adjustments before committing to technical details.
