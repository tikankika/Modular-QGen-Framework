# VALIDATION CHECKLIST

**Version:** 2.0
**Last Updated:** November 2025
**Purpose:** Pre-QTI export validation rules - machine-readable reference for Claude Desktop
**Part of:** 3-document set (BB6A: Output | BB6B: Metadata | BB6C: Validation)

---

## VALIDATION WORKFLOW

```
1. Create question in markdown format
2. Add metadata fields
3. Run validation checklist (this document)
4. Export to QTI Generator for Inspera
```

**Critical:** All checks must pass before QTI export

---

## UNIVERSAL VALIDATION (ALL QUESTIONS)

```
REQUIRED:
- [ ] Question header present (Type, Identifier, Points)
- [ ] Identifier UNIQUE across entire question bank
- [ ] Type code exact match (lowercase_underscores)
- [ ] Question Text section present
- [ ] Question separator (---) at end
- [ ] Feedback section present with required subsections
- [ ] Unanswered Feedback included

FORMAT:
- [ ] Type spelling exact (see BB6B)
- [ ] Identifier format UPPERCASE_UNDERSCORES
- [ ] Points positive integer (no text)
- [ ] No trailing spaces in headers
```

---

## AUTO-GRADED QUESTIONS

```
REQUIRED:
- [ ] Answer or correct answers specified
- [ ] Answer format matches type requirements (see BB6B)
- [ ] Correct Response Feedback present
- [ ] Incorrect Response Feedback present

ANSWER FORMAT:
- Single choice: A (plain letter)
- Multiple choice: A, C, E (comma-space separated)
- Match: 1 → A (arrow notation, one per line)
- True/False: A or B only
```

---

## PARTIAL CREDIT QUESTIONS

```
TYPES REQUIRING PARTIAL CREDIT:
- multiple_response
- text_entry
- inline_choice
- match
- gapmatch / gap_match
- graphicgapmatch_v2
- text_entry_graphic
- composite_editor

REQUIRED:
- [ ] Scoring section present
- [ ] Points per correct item specified
- [ ] Points per incorrect item specified (or penalty)
- [ ] Minimum score specified
- [ ] Partially Correct Feedback present
```

---

## BLANK-TYPE VALIDATION

### fill_in_the_blank
```
REQUIRED:
- [ ] Exactly ONE blank (no more, no less)
- [ ] Blank format: _____ (five underscores)
- [ ] Correct Answer section present
- [ ] Accepted Alternatives list present
- [ ] Case Sensitive field (true/false)
- [ ] Expected Length field (number)

FORBIDDEN:
- [ ] NO {{BLANK-N}} format
- [ ] NO Blanks section with subsections
- [ ] NO Scoring section
- [ ] NO Partially Correct Feedback

IF 2+ BLANKS: Change type to text_entry
```

### text_entry
```
REQUIRED:
- [ ] TWO OR MORE blanks
- [ ] Blank format: {{BLANK-1}}, {{BLANK-2}}, etc.
- [ ] Blanks section with subsections for each blank
- [ ] Each blank has: Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length
- [ ] Sequential numbering (1, 2, 3...)
- [ ] Scoring section present
- [ ] Partially Correct Feedback present

FORBIDDEN:
- [ ] NO _____ format (use {{BLANK-N}})

IF ONLY 1 BLANK: Change type to fill_in_the_blank
```

---

## CHOICE-TYPE VALIDATION

### multiple_choice_single
```
REQUIRED:
- [ ] Min 2 options
- [ ] Options lettered A., B., C., etc.
- [ ] Exactly 1 correct answer
- [ ] Answer matches option letter
```

### multiple_response
```
REQUIRED:
- [ ] Min 3 options
- [ ] Prompt section with "Select all" instruction
- [ ] Min 2 correct answers
- [ ] Answer format: A, C, E (comma-space)
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
```

### true_false
```
REQUIRED:
- [ ] Exactly 2 options
- [ ] Options MUST be: A. True, B. False (or language equivalent)
- [ ] Answer A or B only

LANGUAGE VARIANTS:
- en: True/False
- sv: Sant/Falskt
- no: Sann/Falsk
- da: Sandt/Falsk
```

### inline_choice
```
REQUIRED:
- [ ] Placeholders: {{CHOICE-N}} or {{DROPDOWN N}}
- [ ] Sequential numbering
- [ ] Dropdowns section with subsections
- [ ] Each dropdown: Correct Answer, Options list
- [ ] Min 2 options per dropdown
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
```

---

## MATCH-TYPE VALIDATION

```
REQUIRED:
- [ ] Min 3 premises (left column)
- [ ] Numbered 1, 2, 3...
- [ ] Choices >= Premises (can have distractors)
- [ ] Lettered A, B, C...
- [ ] Answer format: 1 → A (one per line)
- [ ] Each premise exactly one match
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
```

---

## IMAGE-BASED VALIDATION

### hotspot
```
REQUIRED:
- [ ] Image in Question Text: ![alt](path.png)
- [ ] Hotspot Definition section
- [ ] Shape specified (rectangle|circle|polygon)
- [ ] Correct Region Coordinates
- [ ] Coordinates match image dimensions
- [ ] Image file exists at specified path

COORDINATE FORMATS:
- Rectangle: x1,y1,x2,y2
- Circle: cx,cy,r
- Polygon: x1,y1,x2,y2,x3,y3...
```

### graphicgapmatch_v2
```
REQUIRED:
- [ ] Image in Question Text
- [ ] Draggable Items list
- [ ] Hotspot Zones section with subsections
- [ ] Each zone: Shape, Coordinates, Correct Item, Identifier
- [ ] Zone identifiers unique (zone1, zone2, etc.)
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
- [ ] Typically 2-3 distractor items
```

### text_entry_graphic
```
REQUIRED:
- [ ] Image in Question Text
- [ ] Text Entry Zones section with subsections
- [ ] Each zone: Position (x,y), Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length, Identifier
- [ ] Zone identifiers unique (entry1, entry2, etc.)
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
```

---

## GAP-TYPE VALIDATION

### gapmatch / gap_match
```
REQUIRED:
- [ ] Gap format: {{GAP-N}}
- [ ] Sequential numbering
- [ ] Draggable Items list (all available terms)
- [ ] Gaps section with subsections
- [ ] Each gap: Correct Answer, Identifier (gap1, gap2, etc.)
- [ ] More draggable items than gaps (include distractors)
- [ ] Scoring section present
- [ ] Partially Correct Feedback present
```

---

## MANUALLY-GRADED VALIDATION

### text_area
```
REQUIRED:
- [ ] Editor Configuration section
- [ ] Initial lines specified
- [ ] Field width specified
- [ ] Show word count (true/false)
- [ ] Editor prompt present
- [ ] Rubric with point breakdown
- [ ] Sample Answer provided
- [ ] Only 3 feedback types (General, Answered, Unanswered)

FORBIDDEN:
- [ ] NO Correct Response Feedback
- [ ] NO Incorrect Response Feedback
```

### extended_text
```
REQUIRED:
- [ ] Editor Configuration section
- [ ] Initial lines (typically 15-20)
- [ ] Field width (typically 100%)
- [ ] Show word count: true
- [ ] Maximum words (optional)
- [ ] Editor prompt present
- [ ] Scoring Rubric with 4 tiers minimum (Excellent, Good, Satisfactory, Needs Improvement)
- [ ] Grading Notes for Instructor
- [ ] Only 3 feedback types (General, Answered, Unanswered)

FORBIDDEN:
- [ ] NO Correct Response Feedback
- [ ] NO Incorrect Response Feedback
```

### audio_record
```
REQUIRED:
- [ ] Configuration section
- [ ] Upload Prompt
- [ ] Maximum Duration in seconds (typical: 120-300)
- [ ] Allow Re-recording (true/false)
- [ ] Rubric with scoring criteria
- [ ] Sample Response Description
- [ ] Only 3 feedback types (General, Answered, Unanswered)

FORBIDDEN:
- [ ] NO Correct Response Feedback
- [ ] NO Incorrect Response Feedback
```

---

## COMPOSITE-TYPE VALIDATION

### composite_editor
```
REQUIRED:
- [ ] Placeholders: {{TEXT-N}} and/or {{CHOICE-N}}
- [ ] Sub-Questions section with subsections
- [ ] Each interaction: Type (text_entry or choice), Correct Answer, Points
- [ ] For text_entry: Accepted Alternatives, Case Sensitive
- [ ] For choice: Options in Question Text
- [ ] Scoring section (aggregate)
- [ ] Partially Correct Feedback present
```

---

## INFORMATION-TYPE VALIDATION

### nativehtml
```
REQUIRED:
- [ ] Points MUST be 0
- [ ] Configuration section
- [ ] Display: information_block
- [ ] Skippable (true/false)

FORBIDDEN:
- [ ] NO Answer section
- [ ] NO Feedback section
```

---

## COMMON ERRORS

| Error | Type | Fix |
|-------|------|-----|
| Wrong type code spelling | All | Use exact codes from BB6A |
| Non-unique identifiers | All | Check all IDs unique |
| Missing separator --- | All | Add between questions |
| Wrong Answer format | Auto-graded | See BB6B Answer formats |
| Wrong Bloom's spelling | Metadata | Exact: Understand NOT Understanding |
| Missing Partially Correct | MR/Match/TE | Required for partial credit |
| Wrong placeholder format | TE/IC/GM | {{BLANK-1}} NOT {BLANK-1} |
| Coordinates outside image | Hotspot/GGM/TEG | Test on actual image |
| No rubric | Manual-graded | Always include criteria |
| Multiple blanks + FITB type | fill_in_the_blank | Change to text_entry |
| _____ in text_entry | text_entry | Use {{BLANK-N}} |
| Missing Scoring | Partial credit types | Always include |
| {{BLANK-1}} with FITB | fill_in_the_blank | Use _____ or change type |

---

## VALIDATION SEVERITY

```
ERROR (Must fix before export):
- Missing required sections
- Wrong type code
- Non-unique identifiers
- Wrong Answer format
- Missing separator
- Blank-type mismatch

WARNING (Review recommended):
- Missing optional metadata
- Typos in feedback
- Inconsistent formatting
```

---

## CROSS-REFERENCES

**For question structure:** See BB6A - Question Output Specifications
**For metadata formats:** See BB6B - Metadata Requirements
**For output file structure:** See BB6D - Output File Structure

---

**Document Version:** 2.0 (split from BB6_v02)
**Classification:** Machine-readable technical specification for Claude Desktop
