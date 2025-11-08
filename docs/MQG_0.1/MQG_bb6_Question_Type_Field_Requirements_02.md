# QUESTION TYPE FIELD REQUIREMENTS
## Complete Reference for All Question Templates

**Purpose:** This document specifies ALL required and optional fields for each question type. Use this as a checklist when creating questions to ensure nothing is missing.

---

## UNIVERSAL REQUIREMENTS (ALL QUESTION TYPES)

### Required in Every Question

**Question Header:**
```markdown
# Question [N]: [Descriptive Title]

**Type**: [type_code]
**Identifier**: [UNIQUE_ID]
**Points**: [number]
```

**Sections:**
```markdown
## Question Text
[Content]

## Feedback
### General Feedback
### Unanswered Feedback
```

**Separator:**
```markdown
---
```

### Optional in Every Question

```markdown
**Learning Objectives**: LO1, LO2
**Bloom's Level**: Remember|Understand|Apply|Analyze|Evaluate|Create
**Language**: en|sv|no|da
**Difficulty**: easy|medium|hard
**Tags**: [comma-separated keywords]
```

### Critical Format Rules

| Field | Format | Example | ❌ Wrong |
|-------|--------|---------|---------|
| **Type** | lowercase_underscores | `multiple_choice_single` | `Multiple Choice Single` |
| **Identifier** | UPPERCASE_UNDERSCORES | `MC_Q001` | `mc-q-001` |
| **Points** | Positive integer | `2` | `2 points` |
| **Bloom's** | Exact capitalization | `Understand` | `Understanding` |
| **Answer** | Plain letter(s) | `B` or `A, C, E` | `**B**` or `"B"` |

---

## BLANK-TYPE QUESTIONS: DECISION GUIDE

**Two question types handle "fill in the blank" scenarios. Choose the right one:**

### When to Use FILL IN THE BLANK (`fill_in_the_blank`)

✅ **Use when:**
- Question has **EXACTLY ONE** blank
- Want simple visual formatting (underscores show in question)
- All-or-nothing grading (no partial credit needed)
- Simple matching against accepted answers

**Placeholder format**: `_____` (five underscores)

**Example**:
```markdown
The process of _____ converts light energy into chemical energy.
```

**Required sections**: Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length

### When to Use TEXT ENTRY (`text_entry`)

✅ **Use when:**
- Question has **TWO OR MORE** blanks
- Want structured placeholders with clear numbering
- Partial credit for some blanks correct
- Complex scoring rules

**Placeholder format**: `{{BLANK-1}}`, `{{BLANK-2}}`, `{{BLANK-3}}`, etc.

**Example**:
```markdown
The quadratic formula is: x = {{BLANK-1}} ± √({{BLANK-2}} - {{BLANK-3}}) / {{BLANK-4}}
```

**Required sections**: Blanks (with subsections), Scoring, Partially Correct Feedback

---

### Decision Flowchart

```
Question needs blank(s) to fill?
│
├─ ONE blank only?
│  └─ Use fill_in_the_blank
│     • Placeholder: _____
│     • No Scoring section
│     • No Partially Correct Feedback
│
└─ TWO OR MORE blanks?
   └─ Use text_entry
      • Placeholders: {{BLANK-1}}, {{BLANK-2}}, etc.
      • Must have Scoring section
      • Must have Partially Correct Feedback
```

---

### ❌ COMMON MISTAKES TO AVOID

**Mistake 1: Multiple blanks with fill_in_the_blank type**
```markdown
❌ WRONG:
**Type**: fill_in_the_blank

## Question Text
WTW stands for ______-to-______.

## Blank 1
...
## Blank 2
...
```

✅ **FIX: Change to text_entry**
```markdown
✅ CORRECT:
**Type**: text_entry

## Question Text
WTW stands for {{BLANK-1}}-to-{{BLANK-2}}.

## Blanks
### Blank 1
...
### Blank 2
...

## Scoring
...
```

**Mistake 2: Using {{BLANK-N}} with fill_in_the_blank**
```markdown
❌ WRONG:
**Type**: fill_in_the_blank

## Question Text
The answer is {{BLANK-1}}.
```

✅ **FIX: Use correct placeholder format OR change type**
```markdown
✅ OPTION 1 (if single blank):
**Type**: fill_in_the_blank

## Question Text
The answer is _____.

✅ OPTION 2 (if you want structured format):
**Type**: text_entry

## Question Text
The answer is {{BLANK-1}}.

## Blanks
### Blank 1
...

## Scoring
...
```

**Mistake 3: Using text_entry for single blank (overkill)**
```markdown
❌ INEFFICIENT (but technically works):
**Type**: text_entry

## Question Text
The capital is {{BLANK-1}}.

## Blanks
### Blank 1
...

## Scoring
...
```

✅ **BETTER: Use fill_in_the_blank for simplicity**
```markdown
✅ SIMPLER:
**Type**: fill_in_the_blank

## Question Text
The capital is _____.

## Correct Answer
...
```

---

### Quick Comparison Table

| Feature | fill_in_the_blank | text_entry |
|---------|-------------------|------------|
| **Number of blanks** | Exactly 1 | 2 or more |
| **Placeholder format** | `_____` | `{{BLANK-N}}` |
| **Scoring section** | ❌ Not needed | âœ… Required |
| **Partially Correct Feedback** | ❌ Not needed | âœ… Required |
| **Use case** | Simple single-answer | Multiple parts, partial credit |
| **Complexity** | Low | Medium |

---

## TYPE 1: MULTIPLE CHOICE SINGLE

### Type Code
```markdown
**Type**: multiple_choice_single
```

### Complete Required Structure

```markdown
# Question 1: [Title]

**Type**: multiple_choice_single
**Identifier**: [YOUR_ID]
**Points**: [1-5]

## Question Text
[Question prompt]

## Options
A. [Option 1]
B. [Option 2]
C. [Option 3]
D. [Option 4]

## Answer
[Single letter: A, B, C, or D]

## Feedback

### General Feedback
[Context for all students]

### Correct Response Feedback
[When student selects correct answer]

### Incorrect Response Feedback
[When student selects any wrong answer]

### Unanswered Feedback
[When student doesn't answer]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text section
- âœ… Options section (minimum 2, recommend 4)
- âœ… Answer (single letter)
- âœ… Feedback (all 4 subsections)

### Optional But Recommended
- ✨ Option-Specific Feedback (explain why each option is right/wrong)
- ✨ Learning Objectives
- ✨ Bloom's Level

### Enhanced Structure with Option-Specific Feedback

```markdown
## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[Confirmation]

### Incorrect Response Feedback
[General guidance]

### Option-Specific Feedback

**Option A**: [Why this is correct/incorrect]
**Option B**: [Why this is correct/incorrect]
**Option C**: [Why this is correct/incorrect]
**Option D**: [Why this is correct/incorrect]

### Unanswered Feedback
[Prompt to answer]
```

### Rules
- ⚠️ Exactly ONE correct answer
- ⚠️ Minimum 2 options (recommend 4)
- ⚠️ Answer must match an option letter exactly
- ⚠️ Each option on its own line with letter prefix

---

## TYPE 2: MULTIPLE RESPONSE (SELECT ALL)

### Type Code
```markdown
**Type**: multiple_response
```

### Complete Required Structure

```markdown
# Question 2: [Title]

**Type**: multiple_response
**Identifier**: [YOUR_ID]
**Points**: [2-5]

## Question Text
[Question prompt]

## Prompt
Select all that apply.

## Options
A. [Option 1]
B. [Option 2]
C. [Option 3]
D. [Option 4]
E. [Option 5]

## Answer
[Comma-separated letters: A, C, E]

## Scoring
**Type**: partial_credit
**Points per correct selection**: [e.g., 1]
**Penalty per incorrect selection**: [e.g., -0.5 or 0]
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Response Feedback
[Some correct, some wrong or missing]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text section
- âœ… Prompt section (instructions to select all)
- âœ… Options section (minimum 3)
- âœ… Answer (comma-separated letters)
- âœ… Scoring section (type, points/penalties)
- âœ… Feedback (all 5 subsections)

### Optional But Recommended
- ✨ Option-Specific Feedback
- ✨ Learning Objectives
- ✨ Bloom's Level

### Rules
- ⚠️ At least TWO correct answers required
- ⚠️ Minimum 3 options total
- ⚠️ Answer format: `A, C, E` (comma-space separated)
- ⚠️ Must include Scoring section with partial credit rules
- ⚠️ Must include "Partially Correct Response Feedback"

---

## TYPE 3: TRUE/FALSE

### Type Code
```markdown
**Type**: true_false
```

### Complete Required Structure

```markdown
# Question 3: [Title]

**Type**: true_false
**Identifier**: [YOUR_ID]
**Points**: [1-2]

## Question Text
[Statement to evaluate as true or false]

## Options
A. True
B. False

## Answer
[A or B]

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[Confirmation + explanation why statement is true/false]

### Incorrect Response Feedback
[Correction + explanation]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (statement to evaluate)
- âœ… Options (MUST be exactly "A. True" and "B. False")
- âœ… Answer (A or B)
- âœ… Feedback (all 4 subsections)

### Rules
- ⚠️ Options MUST be exactly: "A. True" and "B. False" (or language equivalent)
- ⚠️ Cannot have "sant/falskt" mixed with A/B - use consistent language
- ⚠️ Question Text should be a single declarative statement
- ⚠️ Avoid negations ("NOT true") - confusing

### Language Variations

**English:**
```markdown
## Options
A. True
B. False
```

**Swedish:**
```markdown
## Options
A. Sant
B. Falskt
```

---

## TYPE 4: FILL IN THE BLANK (SINGLE BLANK ONLY)

**Use for**: Questions with exactly ONE blank to fill
**Placeholder format**: `_____` (five underscores)
**Grading**: All-or-nothing (no partial credit)

⚠️ **IMPORTANT**: This type is for **EXACTLY ONE blank only**. For questions with 2+ blanks, use TYPE 5: TEXT ENTRY instead.

### Type Code
```markdown
**Type**: fill_in_the_blank
```

### Complete Required Structure

```markdown
# Question 4: [Title]

**Type**: fill_in_the_blank
**Identifier**: [YOUR_ID]
**Points**: [1-2]

## Question Text
[Text with blank indicated by: _____]

The process of _____ converts light energy into chemical energy.

## Correct Answer
photosynthesis

## Accepted Alternatives
- Photosynthesis
- photo-synthesis
- photosynthetic process

## Case Sensitive
false

## Expected Length
15

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[Confirmation + explanation]

### Incorrect Response Feedback
[Hint without revealing answer]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with blank: _____)
- âœ… Correct Answer
- âœ… Accepted Alternatives (list)
- âœ… Case Sensitive (true/false)
- âœ… Expected Length (number)
- âœ… Feedback (all 4 subsections)

### Rules
- ⚠️ **MUST have EXACTLY ONE blank** (for 2+ blanks, use text_entry)
- ⚠️ Blank indicated by: `_____` (five underscores, NOT `{{BLANK-1}}`)
- ⚠️ Accepted Alternatives as bulleted list with dash prefix
- ⚠️ Case Sensitive must be explicitly stated (true or false)
- ⚠️ Expected Length is character count for UI sizing
- ⚠️ Primary answer under "Correct Answer", variants under "Accepted Alternatives"
- ⚠️ **NO Scoring section** (single correct answer only)
- ⚠️ **NO Partially Correct Feedback** (all-or-nothing grading)
- ⚠️ If you need partial credit or multiple blanks, use text_entry instead

### ❌ WRONG USAGE - Do NOT Do This

```markdown
❌ INCORRECT - Multiple blanks with fill_in_the_blank:

**Type**: fill_in_the_blank  ❌ Wrong type for multiple blanks!

## Question Text
WTW stands for ______-to-______.  ❌ TWO blanks!

## Blank 1  ❌ Should not have Blank subsections!
**Correct Answer**: Well
...

## Blank 2
**Correct Answer**: Wheels
...
```

✅ **CORRECT - Use text_entry for multiple blanks:**
```markdown
**Type**: text_entry  ✅ Correct type

## Question Text
WTW stands for {{BLANK-1}}-to-{{BLANK-2}}.  ✅ Structured placeholders

## Blanks  ✅ Proper structure
### Blank 1
**Correct Answer**: Well
...

### Blank 2
**Correct Answer**: Wheels
...

## Scoring  ✅ Required for text_entry
**Points per correct field**: 0.5
...

## Feedback
...
### Partially Correct Feedback  ✅ Required for text_entry
...
```

---

## TYPE 5: TEXT ENTRY (MULTIPLE BLANKS)

**Use for**: Questions with TWO OR MORE blanks to fill
**Placeholder format**: `{{BLANK-1}}`, `{{BLANK-2}}`, `{{BLANK-3}}`, etc.
**Grading**: Partial credit possible (some blanks correct)

⚠️ **IMPORTANT**: This type is for **TWO OR MORE blanks**. For single-blank questions, use TYPE 4: FILL IN THE BLANK for simplicity.

### Type Code
```markdown
**Type**: text_entry
```

### Complete Required Structure

```markdown
# Question 5: [Title]

**Type**: text_entry
**Identifier**: [YOUR_ID]
**Points**: [2-5]

## Question Text
[Text with placeholders: {{BLANK-1}}, {{BLANK-2}}, etc.]

The quadratic formula is: x = {{BLANK-1}} ± √({{BLANK-2}} - {{BLANK-3}}) / {{BLANK-4}}

## Blanks

### Blank 1
**Correct Answer**: -b
**Accepted Alternatives**:
- -B
- (-b)
**Case Sensitive**: false
**Expected Length**: 5

### Blank 2
**Correct Answer**: b^2
**Accepted Alternatives**:
- b²
- b*b
**Case Sensitive**: false
**Expected Length**: 5

### Blank 3
**Correct Answer**: 4ac
**Accepted Alternatives**:
- 4*a*c
**Case Sensitive**: false
**Expected Length**: 5

### Blank 4
**Correct Answer**: 2a
**Accepted Alternatives**:
- 2*a
**Case Sensitive**: false
**Expected Length**: 5

## Scoring
**Points per correct field**: 0.5
**Points per incorrect field**: 0
**All correct total**: 2
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All blanks correct]

### Partially Correct Feedback
[Some blanks correct]

### Incorrect Response Feedback
[All blanks wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with {{BLANK-N}} placeholders)
- âœ… Blanks section (one subsection per blank)
  - Each blank MUST have:
    - âœ… Correct Answer
    - âœ… Accepted Alternatives (list)
    - âœ… Case Sensitive (true/false)
    - âœ… Expected Length (number)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections including Partially Correct)

### Rules
- ⚠️ **Use for 2+ blanks** (for single blank, use fill_in_the_blank)
- ⚠️ Blanks indicated by: `{{BLANK-1}}`, `{{BLANK-2}}`, etc. (NOT `_____`)
- ⚠️ Must have Blank subsection for EACH placeholder
- ⚠️ Blank numbers must be sequential (1, 2, 3...)
- ⚠️ **Must include Scoring section** with per-field points
- ⚠️ **Must include "Partially Correct Feedback"**
- ⚠️ Cannot use underscore `_____` format (that's for fill_in_the_blank)

### Comparison with fill_in_the_blank

**When to choose text_entry over fill_in_the_blank:**

| Aspect | fill_in_the_blank | text_entry |
|--------|-------------------|------------|
| Number of blanks | 1 only | 2+ |
| Placeholder | `_____` | `{{BLANK-N}}` |
| Scoring needed | ❌ No | âœ… Yes |
| Partial credit | ❌ No | âœ… Yes |

**Example of single blank (don't use text_entry):**
```markdown
❌ OVERKILL - Don't use text_entry for single blank:

**Type**: text_entry

## Question Text
The capital of Sweden is {{BLANK-1}}.

## Blanks
### Blank 1
...

## Scoring
...
```

✅ **SIMPLER - Use fill_in_the_blank instead:**
```markdown
**Type**: fill_in_the_blank

## Question Text
The capital of Sweden is _____.

## Correct Answer
Stockholm
...
```

---

## TYPE 6: INLINE CHOICE (DROPDOWN)

### Type Code
```markdown
**Type**: inline_choice
```

### Complete Required Structure

```markdown
# Question 6: [Title]

**Type**: inline_choice
**Identifier**: [YOUR_ID]
**Points**: [2-4]

## Question Text
[Text with placeholders: {{CHOICE-1}}, {{CHOICE-2}}, etc.]

During photosynthesis, plants convert {{CHOICE-1}} energy into {{CHOICE-2}} energy stored in {{CHOICE-3}}.

## Dropdowns

### CHOICE-1
**Correct Answer**: light
**Options**:
- light
- heat
- mechanical
- electrical

### CHOICE-2
**Correct Answer**: chemical
**Options**:
- chemical
- kinetic
- thermal
- nuclear

### CHOICE-3
**Correct Answer**: glucose
**Options**:
- glucose
- water
- oxygen
- ATP

## Scoring
**Points per correct selection**: 1
**Points per incorrect selection**: 0
**Total points**: 3
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Feedback
[Some correct]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with {{CHOICE-N}} placeholders)
- âœ… Dropdowns section (one subsection per choice)
  - Each choice MUST have:
    - âœ… Correct Answer
    - âœ… Options (list of all dropdown options)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections)

### Rules
- ⚠️ Choices indicated by: {{CHOICE-1}}, {{CHOICE-2}}, etc.
- ⚠️ Must have Dropdown subsection for EACH placeholder
- ⚠️ Choice numbers must be sequential
- ⚠️ First option in list should be the correct answer (for clarity)
- ⚠️ Minimum 2 options per dropdown (recommend 4)

---

## TYPE 7: MATCH (ASSOCIATE PAIRS)

### Type Code
```markdown
**Type**: match
```

### Complete Required Structure

```markdown
# Question 7: [Title]

**Type**: match
**Identifier**: [YOUR_ID]
**Points**: [3-6]

## Question Text
Match each [concept] to its [definition/example].

## Premises (Left Column)
1. [First item to match]
2. [Second item to match]
3. [Third item to match]
4. [Fourth item to match]

## Choices (Right Column)
A. [First choice]
B. [Second choice]
C. [Third choice]
D. [Fourth choice]
E. [Optional distractor - not matched]

## Answer
1 → A
2 → B
3 → C
4 → D

## Scoring
**Type**: partial_credit
**Points per correct match**: 1
**Penalty per incorrect match**: 0
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Response Feedback
[Some correct]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (matching instructions)
- âœ… Premises section (left column items, numbered)
- âœ… Choices section (right column items, lettered)
- âœ… Answer (one pairing per line: 1 → A)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections)

### Optional But Recommended
- ✨ Match-Specific Feedback (explain each correct pairing)

### Rules
- ⚠️ Minimum 3 premises (recommend 4-5)
- ⚠️ Can have more choices than premises (distractors)
- ⚠️ Answer format: `1 → A` or `1 -> A` (one per line)
- ⚠️ Each premise must have exactly ONE match
- ⚠️ Must include "Partially Correct Response Feedback"

---

## TYPE 8: HOTSPOT (CLICK ON IMAGE)

### Type Code
```markdown
**Type**: hotspot
```

### Complete Required Structure

```markdown
# Question 8: [Title]

**Type**: hotspot
**Identifier**: [YOUR_ID]
**Points**: [2-3]

## Question Text
Click on the [specific area/structure] in the image below.

![Image description](path/to/image.png)

## Hotspot Definition
**Shape**: rectangle|circle|polygon
**Correct Region Coordinates**:
- Rectangle: x1,y1,x2,y2 (top-left, bottom-right)
- Circle: cx,cy,r (center-x, center-y, radius)
- Polygon: x1,y1,x2,y2,x3,y3... (vertices)

**Example**:
- Rectangle: 100,150,300,250
- Circle: 200,200,50
- Polygon: 100,100,200,150,150,200

## Feedback

### General Feedback
[Context about the image]

### Correct Response Feedback
[Confirmation when clicked in correct area]

### Incorrect Response Feedback
[Guidance when clicked in wrong area]

### Unanswered Feedback
[Prompt to click]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with image reference)
- âœ… Image (embedded in Question Text)
- âœ… Hotspot Definition section
  - âœ… Shape (rectangle/circle/polygon)
  - âœ… Correct Region Coordinates
- âœ… Feedback (all 4 subsections)

### Rules
- ⚠️ Image must be referenced in Question Text
- ⚠️ Coordinates based on image pixel dimensions
- ⚠️ Only ONE correct region per question
- ⚠️ Shape must be: rectangle, circle, or polygon
- ⚠️ Test coordinates carefully - wrong coordinates = wrong answers marked correct

---

## TYPE 9: GAP MATCH (DRAG TEXT TO GAPS)

### Type Code
```markdown
**Type**: gapmatch
```

### Complete Required Structure

```markdown
# Question 9: [Title]

**Type**: gapmatch
**Identifier**: [YOUR_ID]
**Points**: [3-5]

## Question Text
Drag the correct terms into the gaps below:

[Sentence with gaps marked as: {{GAP-1}}, {{GAP-2}}, etc.]

The {{GAP-1}} converts {{GAP-2}} into {{GAP-3}} during photosynthesis.

## Draggable Items
- chloroplast
- light energy
- chemical energy
- mitochondria
- ATP
- glucose

## Gaps

### GAP-1
**Correct Answer**: chloroplast
**Identifier**: gap1

### GAP-2
**Correct Answer**: light energy
**Identifier**: gap2

### GAP-3
**Correct Answer**: chemical energy
**Identifier**: gap3

## Scoring
**Points per correct gap**: 1
**Points per incorrect gap**: 0
**Total points**: 3
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Feedback
[Some correct]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with {{GAP-N}} placeholders)
- âœ… Draggable Items (list of all available terms)
- âœ… Gaps section (one subsection per gap)
  - Each gap MUST have:
    - âœ… Correct Answer
    - âœ… Identifier (gap1, gap2, etc.)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections)

### Rules
- ⚠️ Gaps indicated by: {{GAP-1}}, {{GAP-2}}, etc.
- ⚠️ Must list ALL draggable items (correct + distractors)
- ⚠️ Typically more draggable items than gaps (3-5 distractors)
- ⚠️ Each gap needs unique identifier
- ⚠️ Gap numbers must be sequential

---

## TYPE 10: GRAPHIC GAP MATCH (DRAG TO IMAGE)

### Type Code
```markdown
**Type**: graphicgapmatch_v2
```

### Complete Required Structure

```markdown
# Question 10: [Title]

**Type**: graphicgapmatch_v2
**Identifier**: [YOUR_ID]
**Points**: [4-6]

## Question Text
Drag the correct labels to the corresponding parts of the diagram:

![Diagram description](path/to/image.png)

## Draggable Items
- Label 1
- Label 2
- Label 3
- Label 4
- Label 5
- Distractor 1
- Distractor 2

## Hotspot Zones

### Zone 1
**Shape**: circle
**Coordinates**: 150,200,25
**Correct Item**: Label 1
**Identifier**: zone1

### Zone 2
**Shape**: rectangle
**Coordinates**: 100,300,200,350
**Correct Item**: Label 2
**Identifier**: zone2

### Zone 3
**Shape**: polygon
**Coordinates**: 250,100,300,120,275,150
**Correct Item**: Label 3
**Identifier**: zone3

### Zone 4
**Shape**: circle
**Coordinates**: 400,250,30
**Correct Item**: Label 4
**Identifier**: zone4

## Scoring
**Points per correct placement**: 1
**Points per incorrect placement**: 0
**Total points**: 4
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Feedback
[Some correct]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with image reference)
- âœ… Image (embedded in Question Text)
- âœ… Draggable Items (list)
- âœ… Hotspot Zones section (one subsection per zone)
  - Each zone MUST have:
    - âœ… Shape (circle/rectangle/polygon)
    - âœ… Coordinates
    - âœ… Correct Item (which draggable goes here)
    - âœ… Identifier (zone1, zone2, etc.)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections)

### Rules
- ⚠️ Must have image in Question Text
- ⚠️ Coordinates based on image pixels
- ⚠️ Each zone needs unique identifier
- ⚠️ Typically have 2-3 distractor items
- ⚠️ Test coordinates carefully before use

---

## TYPE 11: TEXT ENTRY GRAPHIC (TYPE ON IMAGE)

### Type Code
```markdown
**Type**: text_entry_graphic
```

### Complete Required Structure

```markdown
# Question 11: [Title]

**Type**: text_entry_graphic
**Identifier**: [YOUR_ID]
**Points**: [3-5]

## Question Text
Label the parts shown in the diagram by typing in the text boxes:

![Diagram description](path/to/image.png)

## Text Entry Zones

### Zone 1
**Position**: 150,100
**Correct Answer**: Label 1
**Accepted Alternatives**:
- Alternative spelling 1
- Alternative spelling 2
**Case Sensitive**: false
**Expected Length**: 15
**Identifier**: entry1

### Zone 2
**Position**: 300,150
**Correct Answer**: Label 2
**Accepted Alternatives**:
- Alternative spelling 1
**Case Sensitive**: false
**Expected Length**: 20
**Identifier**: entry2

### Zone 3
**Position**: 200,300
**Correct Answer**: Label 3
**Accepted Alternatives**:
- Alternative spelling 1
- Alternative spelling 2
**Case Sensitive**: true
**Expected Length**: 10
**Identifier**: entry3

## Scoring
**Points per correct entry**: 1
**Points per incorrect entry**: 0
**Total points**: 3
**Minimum score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All correct]

### Partially Correct Feedback
[Some correct]

### Incorrect Response Feedback
[All wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with image reference)
- âœ… Image (embedded in Question Text)
- âœ… Text Entry Zones section (one subsection per zone)
  - Each zone MUST have:
    - âœ… Position (x,y coordinates)
    - âœ… Correct Answer
    - âœ… Accepted Alternatives (list)
    - âœ… Case Sensitive (true/false)
    - âœ… Expected Length (number)
    - âœ… Identifier (entry1, entry2, etc.)
- âœ… Scoring section
- âœ… Feedback (all 5 subsections)

### Rules
- ⚠️ Must have image in Question Text
- ⚠️ Position coordinates: x,y from top-left of image
- ⚠️ Each zone needs unique identifier
- ⚠️ Expected Length for UI text box sizing
- ⚠️ Can have different case sensitivity per zone

---

## TYPE 12: TEXT AREA (SHORT RESPONSE)

### Type Code
```markdown
**Type**: text_area
```

### Complete Required Structure

```markdown
# Question 12: [Title]

**Type**: text_area
**Identifier**: [YOUR_ID]
**Points**: [2-5]

## Question Text
[Open-ended question requiring brief written response]

Write 2-3 sentences explaining [concept].

## Editor Configuration
**Initial lines**: 5
**Field width**: 100%
**Show word count**: true
**Editor prompt**: Type your answer here...

## Rubric
[Scoring criteria]

**Full credit (3 points)**:
- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

**Partial credit (1-2 points)**:
- [Basic criteria]

**No credit (0 points)**:
- [Missing/inadequate response]

## Sample Answer
[Example of complete, correct response]

## Feedback

### General Feedback
[Context about what the question assesses]

### Answered Feedback
Thank you for your response. Your answer will be reviewed and graded by the instructor.

### Unanswered Feedback
Please provide an answer to this question.

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with length guidance)
- âœ… Editor Configuration section
  - âœ… Initial lines (number)
  - âœ… Field width (percentage)
  - âœ… Show word count (true/false)
  - âœ… Editor prompt (placeholder text)
- âœ… Rubric (scoring criteria)
- âœ… Sample Answer
- âœ… Feedback (3 subsections: General, Answered, Unanswered)

### Rules
- ⚠️ Manually graded - cannot auto-grade
- ⚠️ Must include clear rubric with point breakdown
- ⚠️ Must provide sample answer for grader reference
- ⚠️ Initial lines typically 5-10 for short responses
- ⚠️ Only 3 feedback types (no Correct/Incorrect)

---

## TYPE 13: EXTENDED TEXT (ESSAY)

### Type Code
```markdown
**Type**: extended_text
```

### Complete Required Structure

```markdown
# Question 13: [Title]

**Type**: extended_text
**Identifier**: [YOUR_ID]
**Points**: [5-15]

## Question Text
[Essay prompt with clear expectations]

Write a 300-500 word essay addressing:
1. [Requirement 1]
2. [Requirement 2]
3. [Requirement 3]

## Editor Configuration
**Initial lines**: 15
**Field width**: 100%
**Show word count**: true
**Maximum words**: 600
**Editor prompt**: Enter your essay here...

## Scoring Rubric

### Excellent (9-10 points)
- [Criterion 1 - highest level]
- [Criterion 2 - highest level]
- [Criterion 3 - highest level]
- [Writing quality - highest level]

### Good (7-8 points)
- [Criterion 1 - good level]
- [Criterion 2 - good level]
- [Criterion 3 - good level]
- [Writing quality - good level]

### Satisfactory (5-6 points)
- [Criterion 1 - basic level]
- [Criterion 2 - basic level]
- [Criterion 3 - basic level]
- [Writing quality - basic level]

### Needs Improvement (0-4 points)
- [Criterion 1 - inadequate]
- [Criterion 2 - inadequate]
- [Criterion 3 - inadequate]
- [Writing quality - inadequate]

## Grading Notes for Instructor
Look for:
- [Key element 1 with details]
- [Key element 2 with details]
- [Key element 3 with details]

Common issues:
- [Issue 1]
- [Issue 2]

## Feedback

### General Feedback
[Context about what the question assesses]

### Answered Feedback
Thank you for your submission. Your essay will be evaluated using the rubric provided.

### Unanswered Feedback
Please provide a complete response addressing all required components.

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with word count guidance and requirements)
- âœ… Editor Configuration section
  - âœ… Initial lines (15-20 for essays)
  - âœ… Field width (100%)
  - âœ… Show word count (true)
  - âœ… Maximum words (optional but recommended)
  - âœ… Editor prompt
- âœ… Scoring Rubric (4 tiers minimum)
  - âœ… Excellent tier
  - âœ… Good tier
  - âœ… Satisfactory tier
  - âœ… Needs Improvement tier
- âœ… Grading Notes for Instructor
- âœ… Feedback (3 subsections: General, Answered, Unanswered)

### Rules
- ⚠️ Manually graded - cannot auto-grade
- ⚠️ Must have detailed multi-tier rubric
- ⚠️ Must include Grading Notes for consistency
- ⚠️ Typically 5-15 points (higher than short response)
- ⚠️ Initial lines 15-20 for visibility
- ⚠️ Only 3 feedback types (no Correct/Incorrect)

---

## TYPE 14: AUDIO RECORD

### Type Code
```markdown
**Type**: audio_record
```

### Complete Required Structure

```markdown
# Question 14: [Title]

**Type**: audio_record
**Identifier**: [YOUR_ID]
**Points**: [3-10]

## Question Text
[Prompt requiring spoken response]

Record your response addressing:
1. [Requirement 1]
2. [Requirement 2]

Maximum recording length: [2-5] minutes.

## Configuration
**Upload Prompt**: Click to record your answer
**Maximum Duration**: [120-300] seconds
**Allow Re-recording**: true|false

## Rubric
[Scoring criteria for audio response]

**Full credit**:
- [Content criterion 1]
- [Content criterion 2]
- [Clarity/delivery criterion]

**Partial credit**:
- [Basic criteria]

**No credit**:
- [Inadequate/missing]

## Sample Response Description
[Description of what a complete response should include]

## Feedback

### General Feedback
[Context about expectations]

### Answered Feedback
Thank you for your recording. Your response will be reviewed and graded by the instructor.

### Unanswered Feedback
Please record your response to this question.

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with time limit and requirements)
- âœ… Configuration section
  - âœ… Upload Prompt
  - âœ… Maximum Duration (seconds)
  - âœ… Allow Re-recording (true/false)
- âœ… Rubric (scoring criteria)
- âœ… Sample Response Description
- âœ… Feedback (3 subsections: General, Answered, Unanswered)

### Rules
- ⚠️ Manually graded - cannot auto-grade audio
- ⚠️ Maximum Duration in seconds (typical: 120-300)
- ⚠️ Must specify if re-recording allowed
- ⚠️ Must include clear rubric
- ⚠️ Only 3 feedback types (no Correct/Incorrect)

---

## TYPE 15: COMPOSITE EDITOR (MIXED INTERACTIONS)

### Type Code
```markdown
**Type**: composite_editor
```

### Complete Required Structure

```markdown
# Question 15: [Title]

**Type**: composite_editor
**Identifier**: [YOUR_ID]
**Points**: [4-10]

## Question Text
[Complex scenario with embedded interactions]

Given the following data:

1. Calculate the mean: {{TEXT-1}}

2. The mean is a measure of:
   {{CHOICE-1}}
   A. Variability
   B. Central tendency
   C. Distribution shape

3. Is this statement true? "The median equals the mean for this dataset"
   {{CHOICE-2}}
   A. True
   B. False

## Sub-Questions

### Sub-Question 1 (Text Entry)
**Type**: text_entry
**Correct Answer**: [answer]
**Accepted Alternatives**:
- [variant1]
- [variant2]
**Case Sensitive**: false
**Points**: 2

### Sub-Question 2 (Multiple Choice)
**Type**: choice
**Correct Answer**: B
**Points**: 1

### Sub-Question 3 (True/False)
**Type**: choice
**Correct Answer**: A
**Points**: 1

## Scoring
**Points per correct sub-question**: varies (see above)
**Total Points**: 4
**Minimum Score**: 0

## Feedback

### General Feedback
[Context]

### Correct Response Feedback
[All sub-questions correct]

### Partially Correct Feedback
[Some sub-questions correct]

### Incorrect Response Feedback
[All sub-questions wrong]

### Unanswered Feedback
[Prompt]

---
```

### Required Fields
- âœ… Question header (Type, Identifier, Points)
- âœ… Question Text (with interaction placeholders)
  - Text entry: {{TEXT-N}}
  - Choice: {{CHOICE-N}}
- âœ… Sub-Questions section (one subsection per interaction)
  - Each MUST have:
    - âœ… Type (text_entry or choice)
    - âœ… Correct Answer
    - âœ… Points
    - For text_entry: âœ… Accepted Alternatives, âœ… Case Sensitive
    - For choice: Options embedded in Question Text
- âœ… Scoring section (aggregate)
- âœ… Feedback (all 5 subsections)

### Rules
- ⚠️ Can mix text_entry and choice interactions
- ⚠️ Each interaction needs unique placeholder
- ⚠️ Must specify points per sub-question
- ⚠️ Options for choice interactions in Question Text, not Sub-Questions
- ⚠️ Must include "Partially Correct Feedback"

---

## TYPE 16: NATIVE HTML (INFORMATION BLOCK)

### Type Code
```markdown
**Type**: nativehtml
```

### Complete Required Structure

```markdown
# Question 16: [Title]

**Type**: nativehtml
**Identifier**: [YOUR_ID]
**Points**: 0

## Question Text
[Informational content - no question asked]

This section provides important context about [topic]:

- [Information point 1]
- [Information point 2]
- [Information point 3]

[Can include images, formatted text, tables, etc.]

## Configuration
**Display**: information_block
**Skippable**: true

---
```

### Required Fields
- âœ… Question header (Type, Identifier)
- âœ… Points (MUST be 0 - not scored)
- âœ… Question Text (informational content)
- âœ… Configuration section
  - âœ… Display (information_block)
  - âœ… Skippable (true/false)

### Rules
- ⚠️ Points MUST be 0 (not a question)
- ⚠️ No Answer section (not interactive)
- ⚠️ No Feedback section (not graded)
- ⚠️ Used for instructions, context, or reading passages
- ⚠️ No interaction required from student

---

## QUICK REFERENCE TABLE

### Required Sections by Type

| Type | Header | Question Text | Type-Specific | Answer | Feedback | Separator | Blanks | Format | Scoring |
|------|--------|---------------|---------------|--------|----------|-----------|--------|--------|---------|
| **Multiple Choice Single** | âœ… | âœ… | Options | âœ… | âœ… | âœ… | - | - | ❌ |
| **Multiple Response** | âœ… | âœ… | Prompt, Options, Scoring | âœ… | âœ… | âœ… | - | - | âœ… |
| **True/False** | âœ… | âœ… | Options (A/B only) | âœ… | âœ… | âœ… | - | - | ❌ |
| **Fill in Blank** | âœ… | âœ… | Correct Answer, Alternatives, Case, Length | - | âœ… | âœ… | **1 only** | `_____` | ❌ |
| **Text Entry** | âœ… | âœ… | Blanks (×N), Scoring | - | âœ… | âœ… | **2+** | `{{BLANK-N}}` | âœ… |
| **Inline Choice** | âœ… | âœ… | Dropdowns (×N), Scoring | - | âœ… | âœ… | - | - | âœ… |
| **Match** | âœ… | âœ… | Premises, Choices, Scoring | âœ… | âœ… | âœ… | - | - | âœ… |
| **Hotspot** | âœ… | âœ… (+ image) | Hotspot Definition | - | âœ… | âœ… | - | - | ❌ |
| **Gap Match** | âœ… | âœ… | Draggables, Gaps (×N), Scoring | - | âœ… | âœ… | - | - | âœ… |
| **Graphic Gap Match** | âœ… | âœ… (+ image) | Draggables, Zones (×N), Scoring | - | âœ… | âœ… | - | - | âœ… |
| **Text Entry Graphic** | âœ… | âœ… (+ image) | Entry Zones (×N), Scoring | - | âœ… | âœ… | - | - | âœ… |
| **Text Area** | âœ… | âœ… | Editor Config, Rubric, Sample | - | âœ… * | âœ… | - | - | ❌ |
| **Extended Text** | âœ… | âœ… | Editor Config, Rubric (4-tier), Grading Notes | - | âœ… * | âœ… | - | - | ❌ |
| **Audio Record** | âœ… | âœ… | Configuration, Rubric, Sample Description | - | âœ… * | âœ… | - | - | ❌ |
| **Composite Editor** | âœ… | âœ… | Sub-Questions (×N), Scoring | - | âœ… | âœ… | - | - | âœ… |
| **Native HTML** | âœ… | âœ… | Configuration | - | - | âœ… | - | - | ❌ |

**\*** = Only 3 feedback types (General, Answered, Unanswered) for manually graded

---

## VALIDATION CHECKLIST

Use this checklist before exporting questions:

### For EVERY Question
- [ ] Question header present with Type, Identifier, Points
- [ ] Identifier is UNIQUE across entire question bank
- [ ] Type code spelled exactly correct (lowercase_underscores)
- [ ] Question Text section present
- [ ] Question separator (---) at end
- [ ] Feedback section present with required subsections
- [ ] Unanswered Feedback included

### For Auto-Graded Questions
- [ ] Answer or correct answers specified
- [ ] Answer format matches type requirements
- [ ] Correct/Incorrect Response Feedback present

### For Multiple-Blank/Choice Types
- [ ] All placeholders have corresponding definition sections
- [ ] Placeholder numbering is sequential
- [ ] Scoring section present with per-item points
- [ ] Partially Correct Feedback included

### For Image-Based Types
- [ ] Image file exists and path is correct
- [ ] Coordinates tested and verified
- [ ] Alt text provided for accessibility

### For Manually-Graded Types
- [ ] Rubric present with clear criteria
- [ ] Sample answer or description provided
- [ ] Editor Configuration specified
- [ ] Only 3 feedback types (no Correct/Incorrect)

### For Match Type
- [ ] Equal or more Choices than Premises
- [ ] All Premises have exactly one match
- [ ] Answer uses → or -> consistently

### For Multiple Response
- [ ] At least 2 correct answers
- [ ] Scoring section with partial credit rules
- [ ] Prompt section with "Select all" instruction

### For Fill-in-the-Blank Questions (fill_in_the_blank)
- [ ] **Exactly ONE blank** (no more, no less)
- [ ] Uses `_____` format (NOT `{{BLANK-1}}`)
- [ ] Has "Correct Answer" section (NOT "Blanks")
- [ ] Has "Accepted Alternatives" list
- [ ] **NO Scoring section** present
- [ ] **NO Partially Correct Feedback** present
- [ ] If 2+ blanks needed, change type to text_entry

### For Text Entry Questions (text_entry)
- [ ] **TWO OR MORE blanks** (for single blank, use fill_in_the_blank)
- [ ] Uses `{{BLANK-1}}`, `{{BLANK-2}}`, etc. (NOT `_____`)
- [ ] Has "Blanks" section with subsections
- [ ] Each blank has: Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length
- [ ] **Scoring section REQUIRED**
- [ ] **Partially Correct Feedback REQUIRED**

---

## COMMON ERRORS TO AVOID

| Error | Impact | Fix |
|-------|--------|-----|
| Wrong type code spelling | Parser fails | Use exact codes from this document |
| Non-unique identifiers | Questions overwrite each other | Check all IDs are unique |
| Missing sections | Conversion fails | Use complete templates |
| Wrong Answer format | Auto-grading fails | Follow exact format rules |
| Missing separator | Questions merge | Always use --- between questions |
| Wrong Bloom's spelling | Metadata inconsistent | Exact: Understand NOT Understanding |
| Missing Partially Correct feedback | MR/Match types incomplete | Required for multi-part questions |
| Wrong placeholder format | Interactions don't work | {{BLANK-1}} NOT {BLANK-1} |
| Coordinates outside image | Hotspots fail | Test coordinates on actual image |
| No rubric for manual grading | Inconsistent grading | Always include detailed rubric |
| **Multiple blanks with fill_in_the_blank** | **Parser/grading fails** | **Change type to text_entry** |
| **Using ______ in text_entry** | **Blanks not recognized** | **Use {{BLANK-N}} format** |
| **Missing Scoring in text_entry** | **Partial credit fails** | **Always include for text_entry** |
| **Using {{BLANK-1}} with fill_in_the_blank** | **Placeholder not replaced** | **Use _____ or change to text_entry** |

---

**Document Version**: 2.0
**Last Updated**: November 2025
**Modular QGen Version**: 3.0
**Purpose**: Field Requirements Reference for All Question Types

**Changes in v2.0**:
- Added decision tree for choosing between fill_in_the_blank and text_entry
- Clarified single vs multiple blank rules
- Updated TYPE 4 (fill_in_the_blank) with explicit single-blank enforcement
- Updated TYPE 5 (text_entry) with multi-blank requirements
- Enhanced Quick Reference Table with blank count and format info
- Added specific validation rules for blank-type questions
- Expanded common errors section with blank-type mistakes
