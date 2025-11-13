# BUILDING BLOCK 3c: STAGE 2 - METADATA FIELD CONFIGURATION

**Component:** Building Block 3c  
**Framework:** Modular Question Generation System  
**Stage:** 2 of 5  
**Purpose:** Capture required technical metadata for assessment

---

## STAGE 2: METADATA FIELD CONFIGURATION

### Purpose

Stage 2 systematically collects required metadata values. Each field serves specific functions in the platform ecosystem and impacts how questions are discovered, managed, and deployed.

---

## REQUIRED METADATA FIELDS

### Assessment Identification

**title:**
- Descriptive name visible in question bank
- Example: "Biology Evolution Assessment"
- Character limit: typically 255 characters

**identifier:**
- Unique identifier across entire system
- Format: COURSE_TOPIC_VERSION
- Example: BIOG001X_evolution_v2
- No spaces, use underscores
- Must be globally unique

**language:**
- ISO 639-1 code
- Must match question content language
- Options: en | sv | no | da | de | fr
- Affects interface localization

### Course Classification

**subject:**
- Course code
- Becomes primary search label
- Example: BIOG001X
- Must match institutional course codes

**academic_level:**
- Options: undergraduate | graduate | professional
- Determines expected student sophistication
- May affect assessment calibration

**academic_year:**
- Current academic year
- Example: 2024-2025 or 2024
- Supports version tracking

### Learning Objectives Mapping

**Total objectives from BB2:** [N]

For each learning objective:
- **ID:** LO1, LO2, LO3, etc.
- **Description:** Full text from BB2
- **Bloom's Level:** Remember/Understand/Apply/Analyze/Evaluate
- **Content Tier:** 1 (essential) / 2 (important) / 3 (enrichment)

**Mapping requirements:**
- All objectives must have unique IDs
- All objectives must have clear descriptions
- Mapping table created for question assignment (completed in BB4)

### Assessment Configuration

**type:**
- Options: formative | summative
- From BB2 assessment strategy
- Affects default feedback and attempt settings

**feedback_mode:**
- Options: immediate | deferred | none
- Determines when students see results
- immediate: After each question
- deferred: After assessment completion
- none: No feedback provided

**duration_minutes:**
- Time limit in minutes
- Enter "0" or "unlimited" for untimed
- From BB2 time constraints

**attempts_allowed:**
- Number of permitted attempts
- Enter specific number or "unlimited"
- From BB2 assessment strategy

---

## METADATA FIELD SUMMARY

```yaml
metadata:
  assessment:
    title: [Assessment title]
    identifier: [COURSE_TOPIC_VERSION]
    language: [ISO code]
  
  course:
    subject: [Course code]
    academic_level: [undergraduate/graduate/professional]
    academic_year: [Year]
  
  learning_objectives:
    total: [N]
    objectives:
      - id: LO1
        description: [Full objective text]
        bloom: [Cognitive level]
        tier: [1/2/3]
      - id: LO2
        description: [Full objective text]
        bloom: [Cognitive level]
        tier: [1/2/3]
      # ... continue for all N objectives
  
  configuration:
    type: [formative/summative]
    feedback_mode: [immediate/deferred/none]
    duration_minutes: [N or unlimited]
    attempts_allowed: [N or unlimited]
```

---

## STAGE 2 COMPLETION CHECKPOINT

**This stage is now complete.**

### Completion Verification
- All required fields populated
- Identifier unique and properly formatted
- Language code correct
- All learning objectives mapped with IDs
- Assessment configuration specified

**Status:** Complete when all metadata collected

**Next stage:** bb3d (Stage 3: Label System Design)

---

**Document Status:** BB3 Stage 2 Complete  
**Component:** Building Block 3c  
**Previous File:** bb3b (Stage 1: Platform Orientation)  
**Next File:** bb3d (Stage 3: Label System Design)  
**Lines:** 145
