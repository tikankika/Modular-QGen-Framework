# BUILDING BLOCK 3: TECHNICAL SETUP

**Component:** Building Block 3  
**Framework:** Modular Question Generation System  
**Classification:** 🔶 STATIC (technical compliance)  
**Primary Input:** Building Block 2 (Assessment Blueprint)  
**Primary Output:** Technical Configuration Document  
**Purpose:** Configure platform-compliant technical metadata  
**Estimated Duration:** 30 minutes

---

## OVERVIEW

Building Block 3 translates the pedagogical assessment blueprint from Building Block 2 into technical specifications required for platform implementation. This component establishes metadata structure, organizational labels, and question type mappings that ensure generated questions function properly within the target Learning Management System.

Unlike the pedagogical dialogue in Building Blocks 1 and 2, Building Block 3 follows predetermined technical specifications. Technical compliance is binary—metadata either meets platform requirements or it does not. This static nature enables efficient configuration through systematic specification rather than iterative refinement.

---

## PROCESS STAGES

### Stage 1: Platform Requirements

Verify target platform and understand technical constraints:

**Platform Identification:**
- Target LMS: [Inspera / Canvas / Moodle / Other]
- Version/capabilities relevant to question types
- Character limits and field constraints
- Import/export format (typically QTI 2.2)

**Critical Understanding:**
- Metadata vs. content distinction
- Label system function (searchable tags)
- Question type codes (exact matching required)
- Required vs. optional fields

### Stage 2: Core Metadata

Establish fundamental identification and classification:

**Assessment Identification:**
```
title: [Descriptive name for question bank]
identifier: [COURSE_TOPIC_VERSION] (unique across system)
language: [ISO 639-1 code: en | sv | no | da | de | fr]
```

**Course Context:**
```
subject: [Course code - becomes primary label]
academic_level: [undergraduate | graduate | professional]
academic_year: [YYYY]
```

**Assessment Configuration:**
```
type: [formative | summative] (from BB2)
feedback_mode: [immediate | deferred | none] (from BB2)
duration_minutes: [X | unlimited]
attempts_allowed: [N | unlimited]
```

**Learning Objectives Registry:**
```
All objectives from BB2 with unique IDs (LO1, LO2, ..., LOn)
Each objective maps to specific questions (assigned in BB4)
```

### Stage 3: Label Architecture

Design searchable organizational structure:

**Required Labels:**
- Course code (matches subject field)
- Major topic(s) relevant to content

**Recommended Labels:**
- Subtopic categorization (2-4 levels)
- Bloom's taxonomy levels (Remember, Understand, Apply, Analyze, Evaluate)
- Learning objective identifiers (LO1, LO2, etc.)

**Optional Labels:**
- Difficulty markers (basic, intermediate, advanced)
- Development status (draft, review, ready)
- Content type indicators (calculation, diagram, scenario)

**Label Formatting Rules:**
- No special prefixes (correct: "LO1" not "LO:LO1")
- Maximum 50 characters per label
- Consistent capitalization
- No special characters except hyphen and underscore

### Stage 4: Question Type Mapping

Map pedagogical question types from BB2 blueprint to platform technical codes:

**Standard Mappings:**
```
Multiple Choice (Single) → multiple_choice_single
Multiple Choice (Multiple) → multiple_response
True/False → true_false
Fill-in-Blank → fib_text
Text Entry → text_entry
Short Answer → text_area
Essay/Extended → extended_text
Matching → match
Ordering → order
Numeric Entry → numeric
Hotspot → hotspot
File Upload → file_upload
```

**Validation:**
- Verify all question types from BB2 supported by platform
- Identify any special configuration requirements
- Confirm scoring implications understood

### Stage 5: Technical Validation

Verify configuration completeness and compliance:

**Completeness:**
- All required metadata fields populated
- All learning objectives have unique IDs
- All question types from BB2 mapped to technical codes
- Label system defined

**Consistency:**
- Identifier unique (no system conflicts)
- Language code matches content language
- Subject field matches course code label
- Question types match BB2 blueprint quantities

**Compliance:**
- Character limits respected
- Required field formats followed
- Platform constraints satisfied
- Institutional requirements met

**Cross-References:**
- Learning objective count matches BB2 output
- Question type distribution matches BB2 blueprint
- Assessment configuration aligns with BB2 strategy

---

## TECHNICAL CONFIGURATION OUTPUT

Building Block 3 produces authoritative technical specifications:

**Core Specifications:**
```markdown
# Technical Configuration: [Title]

Platform: [LMS Name]
Format: QTI 2.2
Language: [ISO Code]
Identifier: [UNIQUE_ID]

## Metadata
subject: [Course Code]
academic_level: [Level]
academic_year: [Year]
type: [formative/summative]
feedback_mode: [immediate/deferred/none]
duration: [X minutes | unlimited]
attempts: [N | unlimited]

## Learning Objectives
LO1: [Description] (Bloom: [Level], Tier: [1/2/3])
LO2: [Description] (Bloom: [Level], Tier: [1/2/3])
...
LOn: [Description] (Bloom: [Level], Tier: [1/2/3])

## Label Architecture
Primary: [course_code]
Topics: [topic1], [topic2], [topic3]
Cognitive: [Remember], [Understand], [Apply], [Analyze], [Evaluate]
LO Tags: [LO1], [LO2], ..., [LOn]
Optional: [difficulty/status markers if used]

## Question Type Codes
[Blueprint Type] → [technical_code] ([N] questions, [auto-scored Y/N])
[Blueprint Type] → [technical_code] ([N] questions, [auto-scored Y/N])
...

Validation: PASSED
Configuration frozen: [Timestamp]
```

---

## INTEGRATION POINTS

### From Building Block 2
- Learning objectives with IDs
- Question type selection
- Assessment strategy (formative/summative)
- Time and attempt limits

### To Building Block 4
- Exact technical codes for question types
- Metadata fields to include in all questions
- Label set to apply consistently
- Learning objective IDs for question assignment

### To Building Block 5
- Technical validation criteria
- Label consistency requirements
- Metadata completeness checks

### To Building Block 6
- QTI export specifications
- Manifest file structure
- Question bank organization

---

## PLATFORM-SPECIFIC NOTES

### Inspera
- Labels become searchable tags in question bank interface
- Certain metadata appears only in manifest files
- Question type codes must match exactly (case-sensitive)
- Character encoding: UTF-8 required

### Canvas
- Labels stored as question tags
- Outcomes can map to learning objectives
- Question bank hierarchy requires folder structure
- Support for most standard QTI types

### Moodle
- Categories serve as organizational structure
- Tags available for additional classification
- Question type plugins may extend standard types
- Import requires XML validation

---

## TRANSITION TO BUILDING BLOCK 4

**Standard Path:**
BB3 complete → Proceed to BB4 (Question Generation)

Technical specifications provide question writers with:
- Exact technical codes to use
- Required metadata structure
- Label set for consistent application
- Learning objective IDs for assignment

**Revision Path:**
If validation reveals platform limitations affecting BB2 design:
- Return to BB2 for design adjustment
- Update BB3 after BB2 revision
- Revalidate technical specifications

---

## BB3 COMPLETION VERIFICATION

Technical configuration ready when:
- All required metadata specified
- Label architecture defined
- Question types mapped to technical codes
- Validation passed (completeness, consistency, compliance)
- Configuration document created
- Integration points with BB2 and BB4 clear

**Status:** Ready to proceed to Building Block 4 (Question Generation)

---

**Document Status:** BB3 Complete  
**Component:** Building Block 3  
**Previous:** bb2h (BB2 Stage 7: Blueprint Construction)  
**Next:** bb4a (BB4 Introduction)  
**Lines:** 220
