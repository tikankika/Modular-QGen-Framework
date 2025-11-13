# BUILDING BLOCK 3e: STAGE 4 - QUESTION TYPE MAPPING

**Component:** Building Block 3e  
**Framework:** Modular Question Generation System  
**Stage:** 4 of 5  
**Purpose:** Map pedagogical question types to platform technical codes

---

## STAGE 4: QUESTION TYPE MAPPING

### Purpose

Stage 4 translates pedagogical question types from the assessment blueprint (Building Block 2) into platform-specific technical codes. This mapping ensures that question functionality matches instructional intent and that all selected types are supported by the target platform.

Accurate type mapping prevents functional mismatches. For instance, mapping a multiple response question (where multiple answers can be correct) to a single choice type would fundamentally alter the assessment's validity.

---

## STANDARD QUESTION TYPE MAPPINGS

### From Assessment Blueprint → Technical Code

**Selected-Response Formats:**
- Multiple Choice (Single Answer) → `multiple_choice_single`
- Multiple Choice (Multiple Answers) → `multiple_response`
- True/False → `true_false`
- Matching → `match`
- Ordering/Sequencing → `order`

**Constructed-Response Formats:**
- Fill-in-Blank → `fib_text`
- Text Entry (Short Answer) → `text_entry`
- Text Area (Essay/Extended) → `text_area`
- Extended Text (Long Essay) → `extended_text`
- Numeric Entry → `numeric`

**Interactive Formats:**
- Hotspot (Image Selection) → `hotspot`
- Inline Choice (Dropdown in Text) → `inline_choice`
- Gap Match (Drag and Drop) → `gap_match`

**Upload Formats:**
- File Upload → `file_upload`

---

## QUESTION TYPES FROM BB2 BLUEPRINT

**Total question types in assessment:** [N]

**Mapping Table:**

| Blueprint Type | Technical Code | Quantity | Auto-Score | Platform Support |
|----------------|----------------|----------|------------|------------------|
| [Type from BB2] | [tech_code] | [N] | Yes/No | Verified |
| [Type from BB2] | [tech_code] | [N] | Yes/No | Verified |
| [Type from BB2] | [tech_code] | [N] | Yes/No | Verified |

---

## PLATFORM COMPATIBILITY VERIFICATION

**For each question type:**

**Platform Support:**
- Verify type is supported by target platform
- Check for version-specific limitations
- Note any special configuration requirements

**Scoring Implications:**
- Auto-scored: System grades automatically
- Manual-scored: Requires instructor grading
- Partial credit: Supported or not

**Student Interface:**
- How will students interact with this type?
- Any accessibility considerations?
- Mobile compatibility?

**Technical Constraints:**
- Character limits for responses
- File size limits for uploads
- Image format requirements for hotspots
- Special syntax requirements

---

## PLATFORM-SPECIFIC NOTES

**Inspera:**
- Supports full range of QTI interaction types
- Strong support for interactive formats
- Robust auto-scoring for most types

**Canvas:**
- Most standard types supported
- Some advanced interactive formats limited
- Good mobile compatibility

**Moodle:**
- Extensive type support through plugins
- Question type availability depends on installed plugins
- Some formats require specific Moodle versions

---

## TECHNICAL CONSTRAINTS DOCUMENTATION

[Document any platform-specific limitations or special requirements:]

- Type [X] requires: [special configuration]
- Type [Y] has limitation: [constraint description]
- Type [Z] needs: [special handling notes]

---

## STAGE 4 COMPLETION CHECKPOINT

**This stage is now complete.**

### Completion Verification
- All question types from BB2 mapped to technical codes
- Platform support verified for all types
- Scoring implications understood
- Special requirements documented
- Technical constraints noted

**Status:** Complete when all question types mapped

**Next stage:** bb3f (Stage 5: Technical Validation)

---

**Document Status:** BB3 Stage 4 Complete  
**Component:** Building Block 3e  
**Previous File:** bb3d (Stage 3: Label System Design)  
**Next File:** bb3f (Stage 5: Technical Validation)  
**Lines:** 115
