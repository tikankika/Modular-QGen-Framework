# QUESTION OUTPUT SPECIFICATIONS

**Version:** 2.0
**Last Updated:** November 2025
**Purpose:** Field requirements for each question type - machine-readable reference for Claude Desktop
**Part of:** 3-document set (BB6A: Output | BB6B: Metadata | BB6C: Validation)

---

## UNIVERSAL REQUIREMENTS

### Required Header Fields
```
Type: lowercase_underscores
Identifier: UPPERCASE_UNDERSCORES
Points: positive integer
```

### Required Sections (All Types)
```
## Question Text
## Feedback
  ### General Feedback
  ### Unanswered Feedback
```

### Separator
```
---
```

### Format Rules
| Field | Format | Valid Example | Invalid Example |
|-------|--------|---------------|-----------------|
| Type | lowercase_underscores | multiple_choice_single | Multiple Choice Single |
| Identifier | UPPERCASE_UNDERSCORES | MC_Q001 | mc-q-001 |
| Points | positive integer | 2 | 2 points |
| Answer | plain letters | B or A, C, E | **B** or "B" |

---

## INSPERA FEEDBACK REQUIREMENT

**CRITICAL:** Inspera platform requires ALL feedback types to contain IDENTICAL content.

```
Implementation: unified_feedback
All feedback subsections receive the same text:
- General Feedback
- Correct Response Feedback
- Incorrect Response Feedback
- Partially Correct Response Feedback
- Unanswered Feedback
```

**Rules:**
- Write ONE comprehensive feedback message
- Message must work for all outcome states
- QTI Generator uses same content for all feedback placeholders
- Do NOT write different messages per state (will be ignored)

**Example:**
```
## Feedback
### General Feedback
Evolution is defined as change in heritable traits of populations over successive generations...
[Full explanation that works regardless of answer correctness]

### Correct Response Feedback
[Same content as General Feedback]

### Incorrect Response Feedback
[Same content as General Feedback]
```

---

## BLANK-TYPE DECISION RULE

### fill_in_the_blank
```
Blanks: Exactly 1
Format: _____
Sections: Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length
Forbidden: Scoring, Partially Correct Feedback
```

### text_entry
```
Blanks: 2 or more
Format: {{BLANK-1}}, {{BLANK-2}}, etc.
Sections: Blanks (with subsections), Scoring
Required: Partially Correct Feedback
```

**Rule:** 1 blank → fill_in_the_blank | 2+ blanks → text_entry

---

## TYPE 1: multiple_choice_single

```
TYPE_CODE: multiple_choice_single

REQUIRED_SECTIONS:
- Question Text
- Options (min 2)
- Answer (single letter)
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Exactly 1 correct answer
- Answer must match option letter
- Options: letter prefix (A., B., C., etc.)

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
```

---

## TYPE 2: multiple_response

```
TYPE_CODE: multiple_response

REQUIRED_SECTIONS:
- Question Text
- Options (min 3)
- Answer (comma-separated letters)
- Scoring (partial_credit)
- Feedback (all subsections identical content)

OPTIONAL_SECTIONS:
- Prompt (default: "Select all that apply")

SCORING_FIELDS:
- Points per correct selection (optional, calculated default)
- Penalty per incorrect selection (optional, default: 0)
- Minimum score (optional, default: 0)

RULES:
- Min 2 correct answers
- Answer format: A, C, E (comma-space separated)

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 3: true_false

```
TYPE_CODE: true_false

REQUIRED_SECTIONS:
- Question Text
- Options (exactly: A. True, B. False)
- Answer (A or B)
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Options MUST be: A. True, B. False (or language equivalent)
- Language variants: en (True/False), sv (Sant/Falskt), no (Sann/Falsk), da (Sandt/Falsk)
- Labels auto-generated from Language field

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
```

---

## TYPE 4: fill_in_the_blank

```
TYPE_CODE: fill_in_the_blank

REQUIRED_SECTIONS:
- Question Text (with _____)
- Correct Answer
- Accepted Alternatives
- Case Sensitive (true/false)
- Feedback (all subsections identical content)

OPTIONAL_SECTIONS:
- Expected Length (default: 15)

RULES:
- MUST have exactly 1 blank
- Blank format: _____ (NOT {{BLANK-1}})
- NO Scoring section
- NO Partially Correct Feedback

FORBIDDEN_SECTIONS:
- Scoring
- Partially Correct Feedback
- Blanks (use Correct Answer instead)

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
IMPLEMENTATION: Uses text_entry template internally
```

---

## TYPE 5: text_entry

```
TYPE_CODE: text_entry

REQUIRED_SECTIONS:
- Question Text (with {{BLANK-N}} placeholders)
- Blanks (for each blank)
  - Correct Answer
  - Accepted Alternatives
  - Case Sensitive
- Scoring (partial_credit)
- Feedback (all subsections identical content)

OPTIONAL_PER_BLANK:
- Expected Length (default: 15)

SCORING_FIELDS:
- Points per correct field (optional, calculated default)
- Points per incorrect field (optional, default: 0)
- Minimum score (optional, default: 0)

RULES:
- MUST have 2+ blanks
- Blank format: {{BLANK-1}}, {{BLANK-2}} (NOT _____)
- Blank numbers sequential (1, 2, 3...)

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 6: inline_choice

```
TYPE_CODE: inline_choice

REQUIRED_SECTIONS:
- Question Text (with {{CHOICE-N}} or {{DROPDOWNN}} placeholders)
- Dropdowns
  - For each dropdown:
    - Correct Answer
    - Options (list)
- Scoring
  - Points per correct selection
  - Points per incorrect selection
  - Total points
  - Minimum score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Placeholders: {{CHOICE-N}} or {{DROPDOWN N}}
- Sequential numbering
- Min 2 options per dropdown

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 7: match

```
TYPE_CODE: match

REQUIRED_SECTIONS:
- Question Text (matching instructions)
- Premises (Left Column) - numbered 1, 2, 3...
- Choices (Right Column) - lettered A, B, C...
- Answer (pairings: 1 → A, 2 → B, etc.)
- Scoring
  - Type: partial_credit
  - Points per correct match
  - Penalty per incorrect match
  - Minimum score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Response Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Min 3 premises
- Choices >= Premises (can have distractors)
- Answer format: 1 → A (one per line)
- Each premise exactly one match

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 8: hotspot

```
TYPE_CODE: hotspot

REQUIRED_SECTIONS:
- Question Text (with image: ![alt](path.png))
- Hotspot Definition
  - Shape (rectangle|circle|polygon)
  - Correct Region Coordinates
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

COORDINATE_FORMATS:
- Rectangle: x1,y1,x2,y2 (top-left, bottom-right)
- Circle: cx,cy,r (center-x, center-y, radius)
- Polygon: x1,y1,x2,y2,x3,y3... (vertices)

RULES:
- Image MUST be in Question Text
- Coordinates based on image pixel dimensions
- ONE correct region per question

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_IMAGE: true
```

---

## TYPE 9: gapmatch

```
TYPE_CODE: gapmatch or gap_match

REQUIRED_SECTIONS:
- Question Text (with {{GAP-N}} placeholders)
- Draggable Items (list of all available terms)
- Gaps
  - For each gap:
    - Correct Answer
    - Identifier (gap1, gap2, etc.)
- Scoring
  - Points per correct gap
  - Points per incorrect gap
  - Total points
  - Minimum score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Gap format: {{GAP-N}}
- Sequential numbering
- More draggable items than gaps (include distractors)

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 10: graphicgapmatch_v2

```
TYPE_CODE: graphicgapmatch_v2

REQUIRED_SECTIONS:
- Question Text (with image: ![alt](path.png))
- Draggable Items (list)
- Hotspot Zones
  - For each zone:
    - Shape (circle|rectangle|polygon)
    - Coordinates
    - Correct Item
    - Identifier (zone1, zone2, etc.)
- Scoring
  - Points per correct placement
  - Points per incorrect placement
  - Total points
  - Minimum score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

COORDINATE_FORMATS:
- Same as hotspot type

RULES:
- Image MUST be in Question Text
- Each zone unique identifier
- Typically 2-3 distractor items

FEEDBACK_SUBSECTIONS: 5
REQUIRES_IMAGE: true
REQUIRES_SCORING: true
REQUIRES_PARTIAL_FEEDBACK: true
```

---

## TYPE 11: text_entry_graphic

```
TYPE_CODE: text_entry_graphic

REQUIRED_SECTIONS:
- Question Text (with image: ![alt](path.png))
- Text Entry Zones
  - For each zone:
    - Position (x,y)
    - Correct Answer
    - Accepted Alternatives
    - Case Sensitive
    - Expected Length
    - Identifier (entry1, entry2, etc.)
- Scoring
  - Points per correct entry
  - Points per incorrect entry
  - Total points
  - Minimum score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Image MUST be in Question Text
- Position: x,y from top-left of image
- Each zone unique identifier

FEEDBACK_SUBSECTIONS: 5
REQUIRES_IMAGE: true
REQUIRES_SCORING: true
REQUIRES_PARTIAL_FEEDBACK: true
```

---

## TYPE 12: text_area

```
TYPE_CODE: text_area

REQUIRED_SECTIONS:
- Question Text (with length guidance)
- Editor Configuration
  - Initial lines
  - Field width
  - Show word count
  - Editor prompt
- Rubric (scoring criteria with point breakdown)
- Sample Answer
- Feedback
  - General Feedback
  - Answered Feedback
  - Unanswered Feedback

RULES:
- Manually graded
- MUST include rubric with point breakdown
- Initial lines typically 5-10

FEEDBACK: Unified content for Answered/Unanswered (no Correct/Incorrect subsections)
MANUALLY_GRADED: true
```

---

## TYPE 13: extended_text

```
TYPE_CODE: extended_text

REQUIRED_SECTIONS:
- Question Text (with word count guidance and requirements)
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
- Feedback
  - General Feedback
  - Answered Feedback
  - Unanswered Feedback

RULES:
- Manually graded
- MUST have multi-tier rubric
- MUST include Grading Notes

FEEDBACK: Unified content for Answered/Unanswered (no Correct/Incorrect subsections)
MANUALLY_GRADED: true
```

---

## TYPE 14: audio_record

```
TYPE_CODE: audio_record

REQUIRED_SECTIONS:
- Question Text (with time limit and requirements)
- Configuration
  - Upload Prompt
  - Maximum Duration (seconds)
  - Allow Re-recording (true/false)
- Rubric (scoring criteria)
- Sample Response Description
- Feedback
  - General Feedback
  - Answered Feedback
  - Unanswered Feedback

RULES:
- Manually graded
- Maximum Duration in seconds (typical: 120-300)
- MUST specify re-recording policy

FEEDBACK: Unified content for Answered/Unanswered (no Correct/Incorrect subsections)
MANUALLY_GRADED: true
```

---

## TYPE 15: composite_editor

```
TYPE_CODE: composite_editor

REQUIRED_SECTIONS:
- Question Text (with interaction placeholders {{TEXT-N}} and {{CHOICE-N}})
- Sub-Questions
  - For each interaction:
    - Type (text_entry or choice)
    - Correct Answer
    - Points
    - For text_entry: Accepted Alternatives, Case Sensitive
    - For choice: Options in Question Text
- Scoring (aggregate)
  - Points per sub-question
  - Total Points
  - Minimum Score
- Feedback
  - General Feedback
  - Correct Response Feedback
  - Partially Correct Feedback
  - Incorrect Response Feedback
  - Unanswered Feedback

RULES:
- Can mix text_entry and choice interactions
- Each interaction unique placeholder
- Points specified per sub-question

FEEDBACK: Unified content for all subsections (see INSPERA FEEDBACK REQUIREMENT)
REQUIRES_SCORING: true
```

---

## TYPE 16: nativehtml

```
TYPE_CODE: nativehtml

REQUIRED_SECTIONS:
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
NOT_INTERACTIVE: true
```

---

## QUICK REFERENCE TABLE

**Note:** All types use unified feedback (see INSPERA FEEDBACK REQUIREMENT)

| Type | Required Sections | Scoring | Image |
|------|------------------|---------|-------|
| multiple_choice_single | Options, Answer | No | No |
| multiple_response | Options, Answer, Scoring | Yes | No |
| true_false | Options (A/B), Answer | No | No |
| fill_in_the_blank | Correct Answer, Alternatives, Case | No | No |
| text_entry | Blanks (×N), Scoring | Yes | No |
| inline_choice | Dropdowns (×N), Scoring | Yes | No |
| match | Premises, Choices, Answer, Scoring | Yes | No |
| hotspot | Hotspot Definition | No | Yes |
| gapmatch | Draggables, Gaps (×N), Scoring | Yes | No |
| graphicgapmatch_v2 | Draggables, Zones (×N), Scoring | Yes | Yes |
| text_entry_graphic | Entry Zones (×N), Scoring | Yes | Yes |
| text_area | Editor Config, Rubric, Sample | No | No |
| extended_text | Editor Config, Rubric (4-tier), Grading Notes | No | No |
| audio_record | Configuration, Rubric, Sample Description | No | No |
| composite_editor | Sub-Questions (×N), Scoring | Yes | No |
| nativehtml | Configuration | No | No |

---

## OPTIONAL CONFIGURATION FIELDS

**Common optional fields with defaults:**

```
Expected Length: 15 (text_entry, fill_in_the_blank)
Prompt: "Select all that apply" (multiple_response)
Shuffle: true (choice-based types)
```

**Type-specific optional fields:**

```
text_area:
- field_width: string (e.g., "100%")
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

**Scoring fields (partial credit types):**
All optional with intelligent defaults:
```
Points per correct: calculated from total points / item count
Points per incorrect: 0
Penalty per incorrect: 0
Minimum score: 0
```

---

## CROSS-REFERENCES

**For metadata field specifications:** See BB6B - Metadata Requirements
**For output file structure:** See BB6D - Output File Structure
**For pre-export validation:** See BB6C - Validation Checklist

---

**Document Version:** 2.0 (split from BB6_v02)
**Classification:** Machine-readable technical specification for Claude Desktop
