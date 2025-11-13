# BUILDING BLOCK 3b: STAGE 1 - PLATFORM ORIENTATION

**Component:** Building Block 3b  
**Framework:** Modular Question Generation System  
**Stage:** 1 of 5  
**Purpose:** Establish understanding of platform requirements and constraints

---

## STAGE 1: PLATFORM ORIENTATION

### Purpose

Stage 1 establishes shared understanding of platform-specific requirements and constraints. This orientation ensures clarity about technical terminology and system behavior before proceeding to configuration.

### Platform Identification

**Target Platform:** [Inspera / Canvas / Moodle / Other: ________]

**Platform Version:** [if relevant]

**Import Format:** QTI 2.2 (standard for most platforms)

### Critical Understanding Points

**Metadata vs. Content Distinction:**
- Metadata: Technical information about questions (identifiers, labels, types)
- Content: Actual question text, answers, feedback

**Label System Function:**
- Labels become searchable tags in question bank
- Enable filtering and discovery
- Support organizational structure

**Question Type Codes:**
- Must match platform's exact technical codes
- Case-sensitive in most systems
- Determines question functionality

**Import/Export Process:**
- QTI XML format standard
- Manifest files contain assessment-level metadata
- Individual question files contain question content

**Character Limits:**
- Platform-specific constraints on field lengths
- Typically 255 characters for labels
- 1000+ for descriptions

### Platform-Specific Notes

**For Inspera:**
- Labels become searchable tags in question bank interface
- Certain metadata appears only in manifest files
- Question type codes must match exactly (case-sensitive)
- Supports full range of QTI interaction types

**For Canvas:**
- Labels stored as question tags
- Question bank hierarchy requires folder structure
- Outcomes can map to learning objectives
- Some advanced QTI features limited

**For Moodle:**
- Categories serve as organizational structure
- Tags available for additional classification
- Question type plugins may extend standard types
- XML validation strict on import

### Institutional Customizations

[Document any special requirements or institutional-specific configurations]

---

## STAGE 1 COMPLETION CHECKPOINT

**This stage is now complete.**

### Completion Verification
- Platform requirements understood
- Technical terminology clear
- Special constraints noted
- Ready to proceed to metadata configuration

**Status:** Complete when platform understanding confirmed

**Next stage:** bb3c (Stage 2: Metadata Field Configuration)

---

**Document Status:** BB3 Stage 1 Complete  
**Component:** Building Block 3b  
**Previous File:** bb3a (Introduction & Foundations)  
**Next File:** bb3c (Stage 2: Metadata Field Configuration)  
**Lines:** 85
