# QUESTION FIELD REQUIREMENTS

**Version:** 3.0
**Last Updated:** November 2025
**Purpose:** Complete field specification for question generation - machine-readable reference for Claude Desktop
**Output Format:** Single markdown file with metadata headers per question

---

## UNIVERSAL METADATA FIELDS

**Required for ALL questions:**

```
**Type**: lowercase_underscores
**Identifier**: UPPERCASE_UNDERSCORES
**Points**: positive integer
**Tags**: comma-separated keywords (must include LO codes, Bloom's Level, Difficulty)
```

**Note:** Learning Objectives, Bloom's Level, and Difficulty are specified WITHIN the Tags field, not as separate metadata fields.

### Field Specifications

#### Type
```
Format: lowercase_underscores
Valid Values:
  multiple_choice_single
  multiple_response
  true_false
  text_entry
  inline_choice
  match
  hotspot
  gapmatch | gap_match
  graphicgapmatch_v2
  text_entry_graphic
  text_area
  extended_text
  audio_record
  composite_editor
  nativehtml

Invalid: CamelCase, Title Case, spaces, hyphens
```

#### Identifier
```
Format: UPPERCASE_UNDERSCORES
Pattern: [A-Z]+(_[A-Z0-9]+)*
Examples:
  - MC_Q001
  - TRA265_L1B_Q001
  - FITB_Q003

Invalid:
  - mc-q-001 (lowercase, hyphens)
  - mcQ001 (mixed case)
  - MC-Q-001 (hyphens)

Rule: MUST be unique across entire question bank
```

#### Points
```
Format: positive integer
Examples: 1, 2, 5, 10
Invalid:
  - 2 points (text suffix)
  - 1.5 (decimals)
  - 0 (except for nativehtml)
  - -1 (negative)

Special: nativehtml MUST have Points: 0
```

#### Tags
```
Format: comma-separated keywords
Purpose: Searchable metadata for question banks AND pedagogical tracking

IMPORTANT: Tags is the ONLY place to specify Learning Objectives, Bloom's Level, and Difficulty.
           There are NO separate metadata fields for these values.

Example (from TRA265):
**Tags**: TRA265, L1b, AY2024-25, Well-to-Wheel, WTT-Stages, LO1, Remember, Easy, Fill-Blank, Auto-Scored, Validated

Structure Breakdown (Required Components):
  1. Course/Module Identifiers: TRA265, L1b, AY2024-25
  2. Content Topic Keywords: Well-to-Wheel, WTT-Stages, fossil-fuels, evolution, etc.
  3. Learning Objective Codes: LO1, LO2, LO3, LO1A, LO1B, etc.
  4. Bloom's Taxonomy Level: Remember, Understand, Apply, Analyze, Evaluate, Create
  5. Difficulty Level: Easy, Medium, Hard
  6. Question Type Category: Fill-Blank, MC-Single, Text-Entry, Matching, etc.
  7. Grading Type: Auto-Scored, Manual-Scoring
  8. Validation Status: Validated, Draft, Reviewed

Bloom's Taxonomy Levels (choose one):
  - Remember: Recall facts and basic concepts
  - Understand: Explain ideas or concepts
  - Apply: Use information in new situations
  - Analyze: Draw connections among ideas
  - Evaluate: Justify a stand or decision
  - Create: Produce new or original work

Difficulty Levels (choose one):
  - Easy: Basic recall or simple application
  - Medium: Requires understanding or multi-step reasoning
  - Hard: Complex analysis, evaluation, or synthesis

Best Practices:
  - REQUIRED: Include LO code(s), Bloom's Level, and Difficulty in every question
  - Include course/module identifiers for organizational filtering
  - Include content topic keywords for searchability
  - Include question type and grading type for administrative filtering
  - Include validation status for quality tracking
  - Recommended 8-12 keywords per question for optimal searchability

Rules:
  - Minimum required tags: Course ID, LO code, Bloom's Level, Difficulty, Grading Type
  - Tags are exported as searchable labels in Inspera LMS
  - Use Title Case for Bloom's Level (Remember, not remember)
  - Use Title Case for Difficulty (Easy, not easy)
  - Use consistent LO code format across questions (e.g., all LO1, LO2, or all LO1A, LO1B)
```

---

## LANGUAGE FIELD (Optional but Recommended)

```
**Language**: en|sv|no|da

Format: ISO 639-1 two-letter code
Valid Values:
  en (English)
  sv (Swedish)
  no (Norwegian)
  da (Danish)

QTI Normalization:
  en → en_us
  sv → sv_se
  no → no_no
  da → da_dk

Usage:
  - Auto-generates labels for true_false questions
  - Sets inspera:defaultLanguage in QTI XML
  - If omitted, defaults to 'en'
```

---

## QUESTION CONTENT SECTIONS

### Universal Required Sections

**All questions MUST have:**

```markdown
## Question Text
[Content here]

## Feedback
### General Feedback
[Content]

### Unanswered Feedback
[Content]
```

### Auto-Graded Questions (Additional Required)

```markdown
### Correct Response Feedback
[Content]

### Incorrect Response Feedback
[Content]
```

### Partial-Credit Questions (Additional Required)

```markdown
### Partially Correct Response Feedback
[Content]

## Scoring
**Type**: partial_credit
**Points per correct item**: number
**Penalty per incorrect item**: number
**Minimum score**: 0
```

### Manually-Graded Questions (Different Feedback Structure)

```markdown
## Feedback
### General Feedback
[Content]

### Answered Feedback
[Content - applies whether correct or not]

### Unanswered Feedback
[Content]
```

**Note:** Manually-graded questions do NOT have Correct/Incorrect feedback subsections

---

## INSPERA UNIFIED FEEDBACK REQUIREMENT

**CRITICAL:** Inspera platform requires ALL feedback subsections to contain IDENTICAL content.

**Implementation:**
```markdown
## Feedback
### General Feedback
Evolution is defined as change in heritable traits of populations over successive generations...

### Correct Response Feedback
Evolution is defined as change in heritable traits of populations over successive generations...

### Incorrect Response Feedback
Evolution is defined as change in heritable traits of populations over successive generations...

### Partially Correct Response Feedback
Evolution is defined as change in heritable traits of populations over successive generations...

### Unanswered Feedback
Evolution is defined as change in heritable traits of populations over successive generations...
```

**Rule:** Write ONE comprehensive feedback message that works for all outcome states.

---

## QUESTION TYPE SPECIFICATIONS

### TYPE 1: multiple_choice_single

```
REQUIRED SECTIONS:
- Question Text
- Options (lettered A., B., C., etc.)
- Answer (single letter: A, B, C, etc.)
- Feedback (4 subsections: General, Correct, Incorrect, Unanswered)

RULES:
- Minimum 2 options
- Exactly 1 correct answer
- Answer must match option letter
- Options use letter prefix (A., B., C., D., etc.)

ANSWER FORMAT:
**Answer**: B
(plain letter, no bold, no quotes)

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
```

**Example:**
```markdown
**Type**: multiple_choice_single
**Identifier**: MC_Q001
**Points**: 1
**Learning Objectives**: LO1
**Bloom's Level**: Remember
**Difficulty**: easy
**Tags**: biology, cells, structure

## Question Text
What is the powerhouse of the cell?

## Options
A. Nucleus
B. Mitochondria
C. Ribosome
D. Golgi apparatus

## Answer
B

## Feedback
### General Feedback
Mitochondria are called the powerhouse of the cell because they produce ATP through cellular respiration...
[Same content repeated in all feedback subsections]
```

---

### TYPE 2: multiple_response

```
REQUIRED SECTIONS:
- Question Text
- Prompt (optional, default: "Select all that apply")
- Options (lettered, min 3)
- Answer (comma-separated letters)
- Scoring (partial credit)
- Feedback (5 subsections including Partially Correct)

RULES:
- Minimum 3 options
- Minimum 2 correct answers
- Answer format: A, C, E (comma-space separated)

ANSWER FORMAT:
**Answer**: A, C, E

SCORING:
**Type**: partial_credit
**Points per correct selection**: 1
**Penalty per incorrect selection**: -0.5
**Minimum score**: 0

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

---

### TYPE 3: true_false

```
REQUIRED SECTIONS:
- Question Text
- Options (MUST be: A. True, B. False)
- Answer (A or B)
- Feedback (4 subsections)

RULES:
- Options MUST be exactly: A. True, B. False (or language equivalent)
- Answer A or B only
- Labels auto-generated from Language field if specified

LANGUAGE VARIANTS:
- en: True/False
- sv: Sant/Falskt
- no: Sann/Falsk
- da: Sandt/Falsk

ANSWER FORMAT:
**Answer**: A

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
```

---

### TYPE 4: text_entry

```
REQUIRED SECTIONS:
- Question Text (with {{BLANK-N}} placeholders)
- Blanks (subsections for each)
  - Correct Answer
  - Accepted Alternatives
  - Case Sensitive
  - Expected Length
- Scoring (partial credit)
- Feedback (5 subsections including Partially Correct)

RULES:
- CAN have 1+ blanks (single blank allowed)
- Blank format: {{BLANK-1}}, {{BLANK-2}}, etc.
- Sequential numbering (1, 2, 3...)
- NO underscore format (_____) - not supported

NOTE: For single-blank questions, use text_entry with one {{BLANK-1}}.
The underscore format (_____) is NOT supported in this implementation.

BLANK FORMAT:
The three stages are: {{BLANK-1}}, {{BLANK-2}}, and {{BLANK-3}}.
Single blank: The acronym "WTW" stands for {{BLANK-1}}.

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

**Example:**
```markdown
**Type**: text_entry
**Identifier**: TE_Q001
**Points**: 3
**Learning Objectives**: LO2
**Bloom's Level**: Remember
**Difficulty**: easy
**Tags**: process, stages

## Question Text
The three main categories are:
1. {{BLANK-1}}
2. {{BLANK-2}}
3. {{BLANK-3}}

## Blank 1
**Correct Answer**: Manufacturing
**Accepted Alternatives**:
- Vehicle manufacturing
- Production
**Case Sensitive**: false
**Expected Length**: 40 characters

## Blank 2
**Correct Answer**: Energy production
**Accepted Alternatives**:
- Fuel production
- Energy carrier production
**Case Sensitive**: false
**Expected Length**: 40 characters

## Blank 3
**Correct Answer**: Disposal
**Accepted Alternatives**:
- Recycling
- End-of-life
**Case Sensitive**: false
**Expected Length**: 30 characters

## Scoring
**Type**: partial_credit
**Points per correct blank**: 1
**Minimum score**: 0

## Feedback
[Unified feedback for all subsections]
```

---

### TYPE 6: inline_choice

```
REQUIRED SECTIONS:
- Question Text (with {{CHOICE-N}} or {{DROPDOWN N}} placeholders)
- Dropdowns (subsections for each)
  - Correct Answer
  - Options (list)
- Scoring
- Feedback (5 subsections)

RULES:
- Placeholders: {{CHOICE-N}} or {{DROPDOWN N}}
- Sequential numbering
- Minimum 2 options per dropdown

PLACEHOLDER FORMAT:
Text {{DROPDOWN1}} more text {{DROPDOWN2}}...

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

---

### TYPE 7: match

```
REQUIRED SECTIONS:
- Question Text
- Premises (Left Column) - numbered 1, 2, 3...
- Choices (Right Column) - lettered A, B, C...
- Answer (pairings: 1 → A, 2 → B, etc.)
- Scoring
- Feedback (5 subsections)

RULES:
- Minimum 3 premises
- Choices >= Premises (can have distractors)
- Answer format: 1 → A (one per line, arrow notation)
- Each premise exactly one match

ANSWER FORMAT:
**Answer**:
1 → A
2 → B
3 → C

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

---

### TYPE 8: hotspot

```
REQUIRED SECTIONS:
- Question Text (with image: ![alt](path.png))
- Hotspot Definition
  - Shape (rectangle|rect|circle|polygon)
  - Correct Region Coordinates
- Feedback (4 subsections)

COORDINATE FORMATS:
RECTANGLE - Three formats accepted:
  1. Corner coordinates: x1=N, y1=N, x2=N, y2=N
  2. Position + dimensions: x=N, y=N, width=N, height=N
  3. Plain format: x1,y1,x2,y2

CIRCLE - Two formats accepted:
  1. Named format: x=N, y=N, radius=N
  2. Plain format: cx,cy,r

POLYGON:
  - Plain format: x1,y1,x2,y2,x3,y3...

SHAPE NAMES:
  - Both "rectangle" and "rect" are accepted (equivalent)
  - Use "circle" for circular regions
  - Use "polygon" for irregular shapes

RULES:
- Image MUST be in Question Text
- Coordinates based on image pixel dimensions
- Multiple hotspots can be defined (mark correct/incorrect)
- Can require multiple clicks (TWO, THREE, etc.)

IMAGE FORMAT:
![Diagram description](images/filename.png)

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_IMAGE: Yes
```

---

### TYPE 9: gapmatch / gap_match

```
REQUIRED SECTIONS:
- Question Text (with {{GAP-N}} placeholders)
- Draggable Items (list)
- Gaps (subsections for each)
  - Correct Answer
  - Identifier (gap1, gap2, etc.)
- Scoring
- Feedback (5 subsections)

RULES:
- Gap format: {{GAP-N}}
- Sequential numbering
- More draggable items than gaps (include distractors)

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

---

### TYPE 10: graphicgapmatch_v2

```
REQUIRED SECTIONS:
- Question Text (with image)
- Draggable Items (list)
- Hotspot Zones (subsections)
  - Shape
  - Coordinates
  - Correct Item
  - Identifier (zone1, zone2, etc.)
- Scoring
- Feedback (5 subsections)

RULES:
- Image MUST be in Question Text
- Each zone unique identifier
- Typically 2-3 distractor items

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_IMAGE: Yes
REQUIRES_SCORING: Yes
```

---

### TYPE 11: text_entry_graphic

```
REQUIRED SECTIONS:
- Question Text (with image)
- Text Entry Zones (subsections)
  - Position (x,y)
  - Correct Answer
  - Accepted Alternatives
  - Case Sensitive
  - Expected Length
  - Identifier (entry1, entry2, etc.)
- Scoring
- Feedback (5 subsections)

RULES:
- Image MUST be in Question Text
- Position: x,y from top-left of image
- Each zone unique identifier

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_IMAGE: Yes
REQUIRES_SCORING: Yes
```

---

### TYPE 12: text_area

```
REQUIRED SECTIONS:
- Question Text (with length guidance)
- Editor Configuration
  - Initial lines
  - Field width
  - Show word count
  - Editor prompt
- Rubric (scoring criteria with point breakdown)
- Sample Answer
- Feedback (3 subsections: General, Answered, Unanswered)

RULES:
- Manually graded
- MUST include rubric with point breakdown
- Initial lines typically 5-10
- NO Correct/Incorrect feedback subsections

FEEDBACK: Only General, Answered, Unanswered (NO Correct/Incorrect)
MANUALLY_GRADED: Yes
```

---

### TYPE 13: extended_text

```
REQUIRED SECTIONS:
- Question Text (with word count guidance)
- Editor Configuration
  - Initial lines (15-20)
  - Field width (100%)
  - Show word count (true)
  - Maximum words (optional)
  - Editor prompt
- Scoring Rubric (4 tiers minimum)
  - Excellent tier
  - Good tier
  - Satisfactory tier
  - Needs Improvement tier
- Grading Notes for Instructor
- Feedback (3 subsections: General, Answered, Unanswered)

RULES:
- Manually graded
- MUST have multi-tier rubric
- MUST include Grading Notes

FEEDBACK: Only General, Answered, Unanswered (NO Correct/Incorrect)
MANUALLY_GRADED: Yes
```

---

### TYPE 14: audio_record

```
REQUIRED SECTIONS:
- Question Text (with time limit and requirements)
- Configuration
  - Upload Prompt
  - Maximum Duration (seconds)
  - Allow Re-recording (true/false)
- Rubric (scoring criteria)
- Sample Response Description
- Feedback (3 subsections: General, Answered, Unanswered)

RULES:
- Manually graded
- Maximum Duration in seconds (typical: 120-300)
- MUST specify re-recording policy

FEEDBACK: Only General, Answered, Unanswered (NO Correct/Incorrect)
MANUALLY_GRADED: Yes
```

---

### TYPE 15: composite_editor

```
REQUIRED SECTIONS:
- Question Text (with {{TEXT-N}} and {{CHOICE-N}} placeholders)
- Sub-Questions (subsections for each)
  - Type (text_entry or choice)
  - Correct Answer
  - Points
  - For text_entry: Accepted Alternatives, Case Sensitive
  - For choice: Options in Question Text
- Scoring (aggregate)
- Feedback (5 subsections)

RULES:
- Can mix text_entry and choice interactions
- Each interaction unique placeholder
- Points specified per sub-question

FEEDBACK: Unified content (see INSPERA REQUIREMENT)
REQUIRES_SCORING: Yes
```

---

### TYPE 16: nativehtml

```
REQUIRED SECTIONS:
- Question Text (informational content)
- Configuration
  - Display: information_block
  - Skippable (true/false)

RULES:
- Points MUST be 0 (not scored)
- NO Answer section
- NO Feedback section
- Used for instructions/context

FEEDBACK: None (information block only)
NOT_INTERACTIVE: Yes
```

---

## QUICK REFERENCE TABLE

| Type | Min Opts | Answer Format | Scoring | Feedback Subsections | Image |
|------|----------|---------------|---------|---------------------|-------|
| multiple_choice_single | 2 | A | No | 4 (GCIAU) | No |
| multiple_response | 3 | A, C, E | Yes | 5 (GCPIU) | No |
| true_false | 2 (A/B) | A or B | No | 4 (GCIAU) | No |
| text_entry | - | N/A | Yes | 5 (GCPIU) | No |
| inline_choice | - | N/A | Yes | 5 (GCPIU) | No |
| match | 3 | 1 → A | Yes | 5 (GCPIU) | No |
| hotspot | - | coords | No | 4 (GCIAU) | Yes |
| gapmatch | - | N/A | Yes | 5 (GCPIU) | No |
| graphicgapmatch_v2 | - | N/A | Yes | 5 (GCPIU) | Yes |
| text_entry_graphic | - | N/A | Yes | 5 (GCPIU) | Yes |
| text_area | - | N/A | No | 3 (GAU) | No |
| extended_text | - | N/A | No | 3 (GAU) | No |
| audio_record | - | N/A | No | 3 (GAU) | No |
| composite_editor | - | N/A | Yes | 5 (GCPIU) | No |
| nativehtml | - | None | No | 0 (none) | No |

**Feedback Key:**
- G = General
- C = Correct Response
- I = Incorrect Response
- P = Partially Correct Response
- A = Answered (manual-graded only)
- U = Unanswered

**Note:** All feedback subsections must contain identical content (Inspera requirement)

---

## OPTIONAL CONFIGURATION FIELDS

### Common Optional Fields

```
Expected Length: 15 (text_entry, fill_in_the_blank)
Prompt: "Select all that apply" (multiple_response)
Shuffle: true (choice-based types)
```

### Type-Specific Optional Fields

```
text_area:
- field_width: "100%"
- editor_prompt: string

extended_text:
- max_words: integer
- editor_prompt: string

audio_record:
- upload_prompt: string

hotspot:
- enable_coloring: true|false
- shape_color: hex color
- shape_opacity: 0.0-1.0

match:
- randomize: true|false
- max_associations: integer
```

### Scoring Fields (Partial Credit Types)

All optional with intelligent defaults:
```
Points per correct: calculated from total points / item count
Points per incorrect: 0
Penalty per incorrect: 0
Minimum score: 0
```

---

## FORMAT RULES SUMMARY

### Metadata Headers
```
- Use **bold** for field names
- Format: **Field Name**: value
- Place ALL metadata at top of question (before ## Question Text)
- Order: Type, Identifier, Points, Learning Objectives, Bloom's Level, Difficulty, Tags, Language (if used)
```

### Section Headers
```
- Use ## for main sections (Question Text, Feedback, Options, etc.)
- Use ### for subsections (General Feedback, Correct Response Feedback, etc.)
- Use #### for sub-subsections if needed (Blank 1, Dropdown 1, etc.)
```

### Question Separators
```
- End each question with:
---
```

### Answer Formats
```
- Single choice: A (plain letter)
- Multiple choice: A, C, E (comma-space separated)
- Match: 1 → A (arrow notation, one per line)
- True/False: A or B only
- Fill-blank/Text-entry: specified in subsections, not Answer field
```

---

## VALIDATION PRIORITIES

### MUST FIX (Errors - will fail QTI generation)
- Missing required metadata fields
- Wrong Type code spelling
- Non-unique Identifiers
- Wrong Answer format
- Missing required sections
- Missing question separator (---)
- Blank-type mismatch (1 blank with text_entry, or 2+ blanks with fill_in_the_blank)

### SHOULD FIX (Warnings - may cause issues)
- Missing optional metadata (Learning Objectives, Bloom's Level, Difficulty)
- Inconsistent formatting
- Typos in feedback
- Missing Inspera unified feedback (different content in subsections)

---

## CROSS-REFERENCES

**For output validation:** See MQG_bb6_Output_Validation_v03.md
**For generation workflow:** See MQG_bb1-5 documents

---

**Document Version:** 3.0 (restructured from 4-way split)
**Classification:** Machine-readable technical specification for Claude Desktop
**Output Format:** Single markdown file with embedded metadata headers
