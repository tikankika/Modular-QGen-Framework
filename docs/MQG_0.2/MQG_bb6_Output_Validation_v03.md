# OUTPUT VALIDATION GUIDE

**Version:** 3.0
**Last Updated:** November 2025
**Purpose:** Validation and analysis guide for question output files - machine-readable reference for Claude Desktop
**Use Case:** Analyze output from bb1-5 generation process, identify issues, suggest improvements

---

## OVERVIEW

This document guides Claude Desktop in validating question output files produced from the MQG bb1-5 generation process.

**Validation Objectives:**
1. Verify all required metadata fields are present
2. Check field formats are correct
3. Ensure question content matches type specifications
4. Identify common errors
5. Suggest specific improvements

**Input:** Single markdown file with questions (e.g., TRA265_L1b_Questions.md)
**Output:** Validation report with error list and improvement suggestions

---

## VALIDATION WORKFLOW

### Step 1: File Structure Check

```
CHECK:
- [ ] File is valid markdown format
- [ ] Questions are separated by --- dividers
- [ ] Each question has metadata headers before content
- [ ] Section headers use proper markdown (##, ###)
```

### Step 2: Question Count and Overview

```
EXTRACT:
- Total number of questions
- Question types distribution
- Points distribution
- Auto-graded vs manual-graded count

REPORT FORMAT:
Total Questions: N
Total Points: N
Auto-Graded: N (X%)
Manual-Graded: N (X%)

Question Types:
- multiple_choice_single: N
- fill_in_the_blank: N
- text_entry: N
...
```

### Step 3: Metadata Validation (Per Question)

For each question, validate ALL metadata fields:

```
REQUIRED FIELDS:
1. **Type**: check against valid values
2. **Identifier**: check uniqueness and format
3. **Points**: check format and value
4. **Learning Objectives**: check presence
5. **Bloom's Level**: check against valid taxonomy
6. **Difficulty**: check against valid values
7. **Tags**: check presence and format

OPTIONAL FIELDS (if present):
8. **Language**: check against valid codes
```

### Step 4: Content Structure Validation (Per Question)

```
CHECK:
- [ ] ## Question Text section exists
- [ ] Type-specific required sections present
- [ ] ## Feedback section exists
- [ ] Required feedback subsections present
- [ ] Question separator (---) at end
```

### Step 5: Type-Specific Validation

Apply validation rules specific to each question type (see Type-Specific Validation section below)

### Step 6: Generate Validation Report

```
REPORT STRUCTURE:
1. Summary Statistics
2. Error List (grouped by severity)
3. Warning List
4. Improvement Suggestions
5. Question-by-Question Details (if errors found)
```

---

## METADATA FIELD VALIDATION

### Type Field

```
VALIDATION:
✓ Field present: **Type**: [value]
✓ Format: lowercase_underscores
✓ Value in valid list (see Field Requirements doc)

COMMON ERRORS:
❌ Wrong case: Multiple_Choice_Single → multiple_choice_single
❌ Spaces: multiple choice single → multiple_choice_single
❌ Hyphens: multiple-choice-single → multiple_choice_single
❌ Typos: mutliple_choice_single → multiple_choice_single

FIX TEMPLATE:
"Question {N}: Type field '{current}' is invalid. Should be '{correct}'."
```

### Identifier Field

```
VALIDATION:
✓ Field present: **Identifier**: [value]
✓ Format: UPPERCASE_UNDERSCORES
✓ Pattern matches: [A-Z]+(_[A-Z0-9]+)*
✓ Unique across all questions

COMMON ERRORS:
❌ Lowercase: mc_q001 → MC_Q001
❌ Mixed case: Mc_Q001 → MC_Q001
❌ Hyphens: MC-Q-001 → MC_Q_001
❌ Duplicate identifiers across questions

FIX TEMPLATE:
"Question {N}: Identifier '{current}' violates format (must be UPPERCASE_UNDERSCORES)."
"Question {N} and {M}: Duplicate identifier '{ID}'. Each identifier must be unique."
```

### Points Field

```
VALIDATION:
✓ Field present: **Points**: [value]
✓ Value is positive integer
✓ No text suffix
✓ Special case: nativehtml MUST be 0

COMMON ERRORS:
❌ Text suffix: 2 points → 2
❌ Decimal: 1.5 → 2 (round to integer)
❌ Zero (except nativehtml): 0 → 1
❌ Negative: -1 → 1

FIX TEMPLATE:
"Question {N}: Points field '{current}' is invalid. Must be positive integer (e.g., '1', '2', '5')."
"Question {N}: nativehtml type must have Points: 0 (currently {current})."
```

### Tags Field

```
VALIDATION:
✓ Field present: **Tags**: [value]
✓ Non-empty value
✓ Minimum recommended: 8-12 keywords

REQUIRED TAGS (Quality Checks):
✓ Learning Objective code(s) - e.g., LO1, LO2, LO1A, LO1B
✓ Bloom's Taxonomy Level - Remember, Understand, Apply, Analyze, Evaluate, or Create (Title Case)
✓ Difficulty Level - Easy, Medium, or Hard (Title Case)
✓ Course/Module identifier - e.g., TRA265, L1b, AY2024-25
✓ Content topic keywords - e.g., Well-to-Wheel, evolution, fossil-fuels
✓ Question type category - e.g., MC-Single, Fill-Blank, Text-Entry
✓ Grading type - Auto-Scored or Manual-Scoring
✓ Validation status - Validated, Draft, or Reviewed

EXPECTED FORMAT (from TRA265 example):
**Tags**: TRA265, L1b, AY2024-25, Well-to-Wheel, WTT-Stages, LO1, Remember, Easy, Fill-Blank, Auto-Scored, Validated

COMMON ERRORS:
❌ Missing Tags field entirely
❌ Empty Tags value
❌ Too few keywords (< 5 minimum, < 8 recommended)
❌ Missing Learning Objective code (REQUIRED)
❌ Missing Bloom's Level (REQUIRED)
❌ Missing Difficulty (REQUIRED)
❌ Wrong case for Bloom's Level (remember → Remember)
❌ Wrong case for Difficulty (easy → Easy, medium → Medium, hard → Hard)
❌ Invalid Bloom's Level (Remembering → Remember, Knowledge → Remember)
❌ Invalid Difficulty value (beginner → Easy, advanced → Hard)

FIX TEMPLATE:
"Question {N}: Missing 'Tags' field (REQUIRED)."
"Question {N}: Tags field is empty. Add required tags: LO code, Bloom's Level, Difficulty, plus course/topic/type/grading/status keywords."
"Question {N}: Tags missing Learning Objective code (REQUIRED). Add LO code (e.g., LO1, LO2, LO1A)."
"Question {N}: Tags missing Bloom's Level (REQUIRED). Add one of: Remember, Understand, Apply, Analyze, Evaluate, Create."
"Question {N}: Tags missing Difficulty (REQUIRED). Add one of: Easy, Medium, Hard."
"Question {N}: Bloom's Level in Tags has wrong case: '{current}' should be '{corrected}' (Title Case)."
"Question {N}: Difficulty in Tags has wrong case: '{current}' should be '{corrected}' (Title Case: Easy, Medium, or Hard)."

SUGGESTIONS:
"Question {N}: Only {count} tags present (recommended 8-12). Consider adding:
  - More content topic keywords (improves searchability)
  - Academic year or semester tag (e.g., AY2024-25, Fall2024)
  - Additional LO codes if question addresses multiple objectives
  - Question format details (e.g., Image-Based, Case-Study, Scenario)"

IMPORTANT: Tags is the ONLY place to specify Learning Objectives, Bloom's Level, and Difficulty.
           There are NO separate metadata fields for these values - everything goes in Tags.
```

### Language Field (Optional)

```
VALIDATION (if present):
✓ Format: two-letter ISO code
✓ Value is: en, sv, no, or da

COMMON ERRORS:
❌ Wrong format: english → en
❌ Wrong code: eng → en
❌ Mixed case: EN → en

FIX TEMPLATE:
"Question {N}: Language '{current}' is invalid. Use two-letter ISO code: en, sv, no, or da."
```

---

## QUESTION CONTENT VALIDATION

### Universal Required Sections

```
ALL QUESTIONS MUST HAVE:
✓ ## Question Text
✓ ## Feedback
  ✓ ### General Feedback
  ✓ ### Unanswered Feedback

COMMON ERRORS:
❌ Missing section headers
❌ Wrong header level (# instead of ##)
❌ Misspelled sections

FIX TEMPLATE:
"Question {N}: Missing required section '## Question Text'."
"Question {N}: Missing required section '## Feedback'."
"Question {N}: Missing feedback subsection '### General Feedback'."
```

### Auto-Graded Questions

```
ADDITIONAL REQUIRED:
✓ ### Correct Response Feedback
✓ ### Incorrect Response Feedback

SPECIAL CASE - Partial Credit:
✓ ### Partially Correct Response Feedback
✓ ## Scoring section

COMMON ERRORS:
❌ Missing Correct/Incorrect feedback
❌ Missing Partially Correct (when type requires it)
❌ Missing Scoring section (partial credit types)

FIX TEMPLATE:
"Question {N} (type: {type}): Missing required feedback subsection '### Correct Response Feedback'."
"Question {N} (type: {type}): Missing required '## Scoring' section for partial credit type."
```

### Manually-Graded Questions

```
FEEDBACK STRUCTURE:
✓ ### General Feedback
✓ ### Answered Feedback
✓ ### Unanswered Feedback

MUST NOT HAVE:
❌ Correct Response Feedback
❌ Incorrect Response Feedback

COMMON ERRORS:
❌ Including Correct/Incorrect feedback (not applicable)
❌ Missing Answered Feedback

FIX TEMPLATE:
"Question {N} (type: {type}): Manual-graded questions should NOT have 'Correct Response Feedback'. Use 'Answered Feedback' instead."
```

### Inspera Unified Feedback Check

```
VALIDATION:
✓ All feedback subsections contain IDENTICAL content

COMMON ERRORS:
❌ Different content in each subsection
❌ Placeholder text like "Correct!" / "Wrong!" / "Partially correct"

WARNING TEMPLATE:
"Question {N}: Feedback subsections contain different content. Inspera requires identical content in ALL feedback subsections. Consider writing one comprehensive explanation that works for all answer states."

QUALITY CHECK:
- Feedback explains the concept regardless of answer correctness
- Feedback is educational, not just confirmatory
- Feedback includes reasoning, not just answer statement
```

---

## TYPE-SPECIFIC VALIDATION

### multiple_choice_single

```
VALIDATE:
✓ ## Options section present
✓ Min 2 options (A., B., ...)
✓ ## Answer section present
✓ Answer format: single letter (A, B, C, etc.)
✓ Answer matches an option letter
✓ Exactly 1 correct answer

COMMON ERRORS:
❌ Answer format: **B** (bold) → B (plain)
❌ Answer format: "B" (quoted) → B (plain)
❌ Answer doesn't match option (Answer: E, but only A-D exist)
❌ Multiple correct answers (use multiple_response instead)

FIX TEMPLATE:
"Question {N}: Answer format should be plain letter (e.g., 'B'), not '{current}'."
"Question {N}: Answer '{answer}' doesn't match any option letter."
"Question {N}: Multiple correct answers detected. Change type to 'multiple_response'."
```

### multiple_response

```
VALIDATE:
✓ ## Options section (min 3)
✓ ## Answer section
✓ Answer format: A, C, E (comma-space separated)
✓ Min 2 correct answers
✓ ## Scoring section present
✓ ### Partially Correct Response Feedback present

COMMON ERRORS:
❌ Answer format: A,C,E (no spaces) → A, C, E
❌ Answer format: A C E (spaces only) → A, C, E
❌ Only 1 correct answer (use multiple_choice_single instead)
❌ Missing Scoring section
❌ Missing Partially Correct feedback

FIX TEMPLATE:
"Question {N}: Answer format for multiple_response must be 'A, C, E' (comma-space separated), not '{current}'."
"Question {N}: Only 1 correct answer. Change type to 'multiple_choice_single' or add more correct answers."
"Question {N}: Missing required '## Scoring' section for partial credit type."
```

### true_false

```
VALIDATE:
✓ ## Options section
✓ Exactly 2 options: A. True, B. False (or language equivalent)
✓ Answer: A or B only

COMMON ERRORS:
❌ Options not exactly "True/False"
❌ More than 2 options
❌ Answer not A or B

FIX TEMPLATE:
"Question {N}: true_false type must have exactly 2 options: 'A. True' and 'B. False'."
"Question {N}: Answer must be 'A' or 'B' for true_false questions, not '{current}'."
```

### fill_in_the_blank

```
VALIDATE:
✓ Question Text contains exactly 1 blank: _____
✓ ## Correct Answer section
✓ ## Accepted Alternatives section
✓ ## Case Sensitive field (true/false)
✓ NO ## Scoring section (forbidden)
✓ NO ### Partially Correct Response Feedback (forbidden)
✓ NOT using {{BLANK-N}} format

COMMON ERRORS:
❌ Multiple blanks (use text_entry instead)
❌ Using {{BLANK-1}} format (use _____ instead)
❌ Including Scoring section (not needed)
❌ Including Partially Correct feedback (not applicable)
❌ Missing Accepted Alternatives

FIX TEMPLATE:
"Question {N}: fill_in_the_blank has {count} blanks. Must have EXACTLY 1 blank. Either remove blanks or change type to 'text_entry'."
"Question {N}: fill_in_the_blank uses wrong format. Use '_____' (five underscores), not '{{BLANK-1}}'."
"Question {N}: fill_in_the_blank should NOT have '## Scoring' section. Remove it."
"Question {N}: Missing '## Accepted Alternatives' section."
```

### text_entry

```
VALIDATE:
✓ Question Text contains 2+ blanks: {{BLANK-1}}, {{BLANK-2}}, etc.
✓ Blanks numbered sequentially (1, 2, 3...)
✓ ## Blanks section with subsections for each
✓ Each blank has: Correct Answer, Accepted Alternatives, Case Sensitive, Expected Length
✓ ## Scoring section present
✓ ### Partially Correct Response Feedback present
✓ NOT using _____ format

COMMON ERRORS:
❌ Only 1 blank (use fill_in_the_blank instead)
❌ Using _____ format (use {{BLANK-N}} instead)
❌ Non-sequential numbering (1, 3, 2 → 1, 2, 3)
❌ Missing Scoring section
❌ Missing Partially Correct feedback

FIX TEMPLATE:
"Question {N}: text_entry has only 1 blank. Change type to 'fill_in_the_blank' or add more blanks."
"Question {N}: text_entry should use '{{BLANK-N}}' format, not '_____'."
"Question {N}: Blank numbering not sequential. Found {{BLANK-{nums}}}. Should be {{BLANK-1}}, {{BLANK-2}}, {{BLANK-3}}."
"Question {N}: Missing required '## Scoring' section for partial credit type."
```

### inline_choice

```
VALIDATE:
✓ Question Text contains {{CHOICE-N}} or {{DROPDOWN N}} placeholders
✓ Sequential numbering
✓ ## Dropdowns section with subsections
✓ Each dropdown has: Correct Answer, Options (min 2)
✓ ## Scoring section present

COMMON ERRORS:
❌ Wrong placeholder format
❌ Non-sequential numbering
❌ Dropdown with only 1 option
❌ Missing Scoring section

FIX TEMPLATE:
"Question {N}: Dropdown {i} has only {count} option(s). Minimum 2 options required."
"Question {N}: Missing '## Dropdowns' section."
```

### match

```
VALIDATE:
✓ ## Premises section (min 3, numbered 1, 2, 3...)
✓ ## Choices section (lettered A, B, C...)
✓ Choices >= Premises
✓ ## Answer section with arrow notation (1 → A)
✓ Each premise exactly one match
✓ ## Scoring section present

COMMON ERRORS:
❌ Wrong answer format: 1-A or 1:A → 1 → A
❌ Fewer choices than premises (no distractors)
❌ Duplicate matches (1 → A, 1 → B)
❌ Missing Scoring section

FIX TEMPLATE:
"Question {N}: Answer format for match type must use arrow notation: '1 → A' (one per line), not '{current}'."
"Question {N}: {count} premises but only {count2} choices. Add distractor choices (Choices should be >= Premises)."
```

### hotspot

```
VALIDATE:
✓ Question Text contains image: ![alt](path.png)
✓ ## Hotspot Definition section
✓ Shape specified (rectangle|circle|polygon)
✓ Correct Region Coordinates

COMMON ERRORS:
❌ Missing image in Question Text
❌ Invalid shape type
❌ Wrong coordinate format
❌ Missing Hotspot Definition

FIX TEMPLATE:
"Question {N}: hotspot type requires image in Question Text. Use format: ![description](images/filename.png)"
"Question {N}: Missing '## Hotspot Definition' section."
"Question {N}: Shape '{shape}' is invalid. Must be: rectangle, circle, or polygon."
```

### Image-Based Types (graphicgapmatch_v2, text_entry_graphic)

```
VALIDATE:
✓ Question Text contains image
✓ Type-specific sections present
✓ ## Scoring section present
✓ Zone/region identifiers unique

COMMON ERRORS:
❌ Missing image
❌ Duplicate zone identifiers
❌ Missing Scoring section

FIX TEMPLATE:
"Question {N}: {type} requires image in Question Text."
"Question {N}: Duplicate zone identifier '{id}'. Each zone must have unique identifier."
```

### Manually-Graded Types (text_area, extended_text, audio_record)

```
VALIDATE:
✓ ## Editor Configuration OR ## Configuration section
✓ ## Rubric OR ## Scoring Rubric section
✓ Sample Answer OR Sample Response Description
✓ Feedback has only 3 subsections (General, Answered, Unanswered)
✓ NO Correct/Incorrect/Partially Correct feedback

SPECIAL FOR extended_text:
✓ Rubric has minimum 4 tiers
✓ ## Grading Notes for Instructor section

COMMON ERRORS:
❌ Missing rubric
❌ Including Correct/Incorrect feedback (not applicable)
❌ Missing Grading Notes (extended_text)
❌ Rubric with fewer than 4 tiers (extended_text)

FIX TEMPLATE:
"Question {N}: Missing '## Rubric' section. Manual-graded questions require scoring criteria."
"Question {N}: Manual-graded questions should NOT have 'Correct Response Feedback'. Remove this subsection."
"Question {N} (extended_text): Rubric must have minimum 4 tiers. Current: {count} tiers."
```

### nativehtml

```
VALIDATE:
✓ Points: 0
✓ NO ## Answer section
✓ NO ## Feedback section
✓ ## Configuration section

COMMON ERRORS:
❌ Points not 0
❌ Including Answer section
❌ Including Feedback section

FIX TEMPLATE:
"Question {N}: nativehtml type must have Points: 0 (currently {current})."
"Question {N}: nativehtml should NOT have '## Answer' section. This is an information block, not a question."
"Question {N}: nativehtml should NOT have '## Feedback' section."
```

---

## COMMON ERRORS AND FIXES

### Error Category: Missing Fields

```
ERROR: Missing required metadata field

EXAMPLES:
- Missing **Type** field
- Missing **Identifier** field
- Missing **Points** field

FIX TEMPLATE:
"Question {N}: Missing required field '{field_name}'. Add this field to question metadata."

SEVERITY: Error (must fix)
```

### Error Category: Format Violations

```
ERROR: Field value doesn't match required format

EXAMPLES:
- Type: Multiple Choice Single (should be multiple_choice_single)
- Identifier: mc-q-001 (should be MC_Q_001)
- Points: 2 points (should be 2)

FIX TEMPLATE:
"Question {N}: Field '{field}' has invalid format '{current}'. Should be '{correct}'."

SEVERITY: Error (must fix)
```

### Error Category: Duplicate Identifiers

```
ERROR: Same identifier used for multiple questions

DETECTION:
Track all identifiers, report duplicates

FIX TEMPLATE:
"Questions {N1} and {N2} have duplicate identifier '{ID}'. Each identifier must be unique. Suggest: {ID}_V2 for question {N2}."

SEVERITY: Error (must fix)
```

### Error Category: Missing Required Sections

```
ERROR: Question missing required content sections

EXAMPLES:
- Missing ## Question Text
- Missing ## Feedback
- Missing ## Options (for choice-based types)
- Missing ## Scoring (for partial credit types)

FIX TEMPLATE:
"Question {N}: Missing required section '## {section_name}' for type '{type}'."

SEVERITY: Error (must fix)
```

### Error Category: Type Mismatch

```
ERROR: Question content doesn't match declared type

EXAMPLES:
- Type: fill_in_the_blank but has multiple blanks (should be text_entry)
- Type: multiple_choice_single but has 2+ correct answers (should be multiple_response)
- Type: multiple_response but has only 1 correct answer (should be multiple_choice_single)

FIX TEMPLATE:
"Question {N}: Content doesn't match type '{current_type}'. {explanation}. Suggested type: '{suggested_type}'."

SEVERITY: Error (must fix)
```

### Error Category: Feedback Quality Issues

```
ERROR: Feedback subsections have different content (violates Inspera requirement)

WARNING TEMPLATE:
"Question {N}: Feedback subsections contain different content. Inspera platform requires ALL feedback subsections to have IDENTICAL content. Recommendation: Write one comprehensive explanatory feedback that works for all answer states."

SEVERITY: Warning (should fix for Inspera compatibility)
```

### Error Category: Alignment Issues

```
ERROR: Bloom's Level and Difficulty misaligned

EXAMPLES:
- Bloom's Level: Analyze with Difficulty: easy (unlikely)
- Bloom's Level: Remember with Difficulty: hard (unlikely)

WARNING TEMPLATE:
"Question {N}: Potential misalignment: Bloom's Level '{bloom}' typically aligns with Difficulty '{expected}', but current Difficulty is '{current}'. Review difficulty assessment."

SEVERITY: Warning (review recommended)
```

### Error Category: Incomplete Alternatives

```
ERROR: Missing or insufficient accepted alternatives for fill-in-blank/text-entry

WARNING TEMPLATE:
"Question {N}: Only {count} accepted alternative(s) provided. Consider adding more variations (capitalization, spelling variations, synonyms) to improve student experience."

SEVERITY: Warning (quality improvement)
```

---

## VALIDATION REPORT FORMAT

### Report Structure

```markdown
# VALIDATION REPORT: {filename}

**Validation Date**: {date}
**Total Questions**: {count}
**Questions Analyzed**: {count}

---

## SUMMARY

**Overall Status**: ✅ PASS | ⚠️ WARNINGS | ❌ ERRORS

**Statistics:**
- Total Points: {sum}
- Auto-Graded: {count} ({percent}%)
- Manual-Graded: {count} ({percent}%)
- Question Types: {unique_count} different types

**Quality Metrics:**
- Questions with errors: {count}
- Questions with warnings: {count}
- Questions validated successfully: {count}

---

## ERRORS (Must Fix)

{If no errors: "✅ No errors found."}

{If errors exist:}
### Question {N}: {question_identifier}

**Errors:**
1. Missing required field 'Learning Objectives'
2. Type field format invalid: 'Multiple Choice Single' should be 'multiple_choice_single'
3. Identifier format invalid: 'mc-q-001' should be 'MC_Q_001'

**Fix Priority**: High

---

## WARNINGS (Should Fix)

{If no warnings: "✅ No warnings."}

{If warnings exist:}
### Question {N}: {question_identifier}

**Warnings:**
1. Feedback subsections contain different content (Inspera compatibility issue)
2. Only 1 accepted alternative provided (consider adding more variations)
3. Bloom's Level 'Analyze' with Difficulty 'easy' may be misaligned

**Fix Priority**: Medium

---

## IMPROVEMENT SUGGESTIONS

{If no suggestions: "No additional suggestions."}

{If suggestions exist:}
### Content Quality

1. **Unified Feedback**: {count} questions have varying feedback across subsections. For Inspera compatibility, use identical content in all feedback subsections.

2. **Tag Enhancement**: {count} questions have fewer than 5 tags. Consider adding more keywords for better searchability (course code, module, topic, question type, grading method).

3. **Alternatives**: {count} fill-in-blank/text-entry questions have minimal accepted alternatives. Add spelling variations, capitalization variants, and synonyms.

### Metadata Consistency

1. **Learning Objectives**: Ensure all objectives (e.g., LO1, LO2) are documented in course learning outcomes.

2. **Identifier Scheme**: Consider adopting consistent identifier pattern across all questions (e.g., {COURSE}_{MODULE}_Q{NUM}).

---

## QUESTION-BY-QUESTION DETAILS

{If all questions validated successfully: "All questions validated successfully. No issues found."}

{If issues exist, list each question with issues:}

### Question 1: MC_Q001
**Type**: multiple_choice_single
**Status**: ✅ Valid

### Question 2: FITB_Q002
**Type**: fill_in_the_blank
**Status**: ⚠️ Warnings
**Issues:**
- Only 1 accepted alternative (recommend 3-5)
- Feedback subsections differ (Inspera compatibility)

### Question 3: TE_Q003
**Type**: text_entry
**Status**: ❌ Errors
**Issues:**
- Missing ## Scoring section
- Missing ### Partially Correct Response Feedback
- Blank numbering not sequential (found {{BLANK-1}}, {{BLANK-3}})

---

## NEXT STEPS

{If errors exist:}
1. **Fix Errors**: Address all {error_count} errors listed above (required for QTI generation)
2. **Review Warnings**: Consider fixing {warning_count} warnings for quality and compatibility
3. **Apply Suggestions**: Implement improvement suggestions for enhanced question quality

{If no errors:}
1. **Review Warnings**: {warning_count} warnings identified - review for quality improvement
2. **Apply Suggestions**: Consider implementing suggestions for enhanced metadata and content
3. **Ready for QTI Export**: File structure validated, can proceed to QTI generation

---

**Validation Complete**
```

---

## SYSTEMATIC VALIDATION CHECKLIST

Use this checklist when analyzing output files:

### Pre-Validation
- [ ] Confirm file is markdown format
- [ ] Confirm file contains question content
- [ ] Count total questions (separated by ---)

### Per-Question Validation
- [ ] Check all required metadata fields present
- [ ] Validate metadata field formats
- [ ] Check identifier uniqueness (across all questions)
- [ ] Verify question content structure
- [ ] Apply type-specific validation rules
- [ ] Check feedback structure
- [ ] Verify unified feedback (Inspera requirement)
- [ ] Check question separator present

### Post-Validation
- [ ] Compile error list
- [ ] Compile warning list
- [ ] Generate improvement suggestions
- [ ] Calculate summary statistics
- [ ] Format validation report

---

## SUGGESTIONS FRAMEWORK

### When to Suggest Changes

```
SUGGEST when:
- Metadata quality can be improved (more tags, better alignment)
- Content quality can be enhanced (more alternatives, better feedback)
- Inspera compatibility can be improved (unified feedback)
- Consistency can be increased (identifier patterns, objective coding)

DO NOT SUGGEST when:
- Field is optional and reasonably omitted
- Current format is acceptable (even if alternative exists)
- Change would be purely cosmetic
```

### Suggestion Priority Levels

```
HIGH PRIORITY:
- Inspera compatibility (unified feedback)
- Type mismatches (wrong type for content)
- Alignment issues (Bloom's vs Difficulty)

MEDIUM PRIORITY:
- Tag enhancement (fewer than 5 tags)
- Alternative expansion (fewer than 3 alternatives)
- Missing optional fields that improve quality

LOW PRIORITY:
- Formatting consistency
- Identifier pattern standardization
- Minor wording improvements
```

### Suggestion Tone

```
GOOD:
"Consider adding more accepted alternatives to improve student experience and reduce false negatives."

"For Inspera compatibility, use identical content in all feedback subsections. This ensures consistent student experience across answer states."

BAD:
"You must add more alternatives."
"This is wrong - fix it immediately."

TONE GUIDELINES:
- Explanatory (why it matters)
- Constructive (how to improve)
- Respectful (acknowledge current work)
- Specific (concrete action items)
```

---

## CROSS-REFERENCES

**For field specifications:** See MQG_bb6_Field_Requirements_v03.md
**For generation workflow:** See MQG_bb1-5 documents

---

**Document Version:** 3.0 (restructured from 4-way split)
**Classification:** Machine-readable validation guide for Claude Desktop
**Use Case:** Analyze and improve question output files from MQG generation process
