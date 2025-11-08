# Changelog

All notable changes to Modular QGen Framework are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### 2025-11-06 - MQG_bb6 Specification v2.0

#### Added
- **MQG_bb6_Question_Type_Field_Requirements_02.md** - Enhanced specification with blank-type clarity
  - **New Decision Guide Section**: "BLANK-TYPE QUESTIONS: DECISION GUIDE" added before TYPE 1
    - Clear flowchart: 1 blank → `fill_in_the_blank`, 2+ blanks → `text_entry`
    - When to use each type with concrete examples
    - 3 common mistakes with wrong/correct examples
    - Quick comparison table showing key differences
  - **TYPE 4 Updates (FILL IN THE BLANK - SINGLE BLANK ONLY)**:
    - Title changed to emphasize "SINGLE BLANK ONLY"
    - Added explicit rule: "MUST have EXACTLY ONE blank"
    - Added rules: "NO Scoring section" and "NO Partially Correct Feedback"
    - New "❌ WRONG USAGE" section showing multiple blanks mistake
    - Provides corrected example using `text_entry` instead
  - **TYPE 5 Updates (TEXT ENTRY - MULTIPLE BLANKS)**:
    - Added introduction: "Use for: TWO OR MORE blanks"
    - Updated rules to emphasize "Use for 2+ blanks"
    - Added "Comparison with fill_in_the_blank" section
    - Shows overkill example of using `text_entry` for single blank
  - **Quick Reference Table Enhanced**:
    - Added "Blanks" column showing "1 only" vs "2+"
    - Added "Format" column showing `_____` vs `{{BLANK-N}}`
    - Added "Scoring" column for all question types
  - **Validation Checklist Expanded**:
    - New section: "For Fill-in-the-Blank Questions" with 7 checks
    - New section: "For Text Entry Questions" with 6 checks
    - Specific format validation for each blank type
  - **Common Errors Section Updated**:
    - Added 4 blank-type specific errors (highlighted in bold):
      - Multiple blanks with fill_in_the_blank
      - Using `______` in text_entry
      - Missing Scoring in text_entry
      - Using `{{BLANK-1}}` with fill_in_the_blank
  - **Document Statistics**: v01: 1533 lines → v02: 1834 lines (~300 lines added)

- **QTI Generator Integration**
  - Validation script (`validate_mqg_format.py`) created in QTI-Generator-for-Inspera repo
  - Validates markdown files against MQG_bb6 v2.0 specifications before QTI generation
  - Detects ambiguous usage: `fill_in_the_blank` with multiple blanks
  - Reports missing required sections: Scoring, Partially Correct Feedback
  - Tested with TRA265 file: 11 errors found in 3 questions
  - Enables quality control checkpoint in question authoring workflow

#### Impact
- **Eliminates ambiguity** between `fill_in_the_blank` and `text_entry` question types
- **Prevents TRA265-style errors** (multiple blanks with wrong type code)
- **Provides clear guidance** for Claude Desktop when generating questions
- **Validation integration** catches format errors before costly QTI generation/import cycle

#### Files Changed
- Created: `docs/MQG_0.1/MQG_bb6_Question_Type_Field_Requirements_02.md`
- Reference: QTI-Generator-for-Inspera `validate_mqg_format.py`

---

### Changed
- **🚨 CRITICAL: Inspera Platform Feedback Requirement Discovered** (2025-11-04)
  - **Discovery**: Through QTI Generator testing (Evolution quiz, 61 questions), identified that Inspera requires ALL FOUR feedback fields to contain EXACTLY THE SAME TEXT
  - **Impact**: When authoring questions for Inspera export, all feedback fields (correct, incorrect, partial, unanswered) must have identical content
  - **QTI Generator Response**: v08 now automatically uses unified feedback by copying the 'correct' field text to all four states
  - **Authoring Guidance Updated**:
    - ❌ **Avoid**: correct="Correct!", incorrect="Wrong!", partial="Partially correct"
    - ✅ **Use**: All fields with comprehensive explanatory text (e.g., "Evolution is defined as... [full explanation]")
    - Write ONE feedback message that works for all outcome states
  - **Platform-Specific**: This is an Inspera limitation, not part of QTI 2.2 standard (which allows different feedback per state)
  - **Future Consideration**: Inspera has been contacted about this limitation; may be enhanced in future platform updates
  - **Documentation Updated**: bb6 Question Type Field Requirements now includes Inspera feedback constraints
  - **Reference**: See QTI-Generator-for-Inspera CHANGELOG.md (2025-11-04 Session 4) for full technical investigation details

### Planned
- Extract Components 3, 5, 6 into separate documentation files
- Additional workflow examples beyond Evolution case study
- Video tutorials for each component
- Template library for common question types
- Multi-language support for international users
- Workflow decision tree diagram

---

## [0.0.1] - 2025-11-04

### Added
- Initial public release of Modular QGen Framework
- **6-component modular architecture**
  - Component 1: Content Analysis (dynamic) - Understand what was taught
  - Component 2: Assessment Design (dynamic) - Define what to assess
  - Component 3: Technical Setup (static) - Configure metadata
  - Component 4: Question Generation (hybrid) - Create questions
  - Component 5: Quality Assurance (hybrid) - Validate quality
  - Component 6: Export/Integration (static) - Convert & import
- **5 proven workflows** for different starting contexts
  - Workflow A: Content-Driven ("I have teaching materials")
  - Workflow B: Standards-Driven ("I must align to curriculum standards")
  - Workflow C: Question-First ("I know what I want to ask")
  - Workflow D: Revision-Driven ("I have old assessments to improve")
  - Workflow E: Technical-First ("I'm migrating to new LMS")
- Evolution case study documentation (72 questions, 5-8 hours)
- Universal QTI Input Specification
- Gap Analysis methodology with real examples
- Complete component documentation (Components 1, 2, 4 as separate files)
- Decision framework for workflow selection

### Documentation
- README.md with Quick Start guide
- LICENSE under CC BY 4.0 International
- CHANGELOG.md following Keep a Changelog format
- Archive of v2.0 framework and process documentation

### Notes
- Framework validated through Evolution QTI project implementation
- Based on v3.0 Component Architecture
- Early-stage release (v0.0.1) - feedback welcome
- Documentation in English for international accessibility
- Time-tested: 5-8 hours for 40-50 quality questions

---

## Pre-Release History

### v3.0 - Component Architecture (2025-11-02)
- Transition from linear process to modular components
- Introduction of component types (Dynamic, Static, Hybrid)
- Addition of Gap Analysis checkpoint after Component 4
- Real-world validation through Evolution project
- 60 → 72 question expansion case study
- 5 workflow patterns identified and documented

### v2.0 - Process-Based Approach (2025-10-XX)
- Original framework structure
- Linear phase-based approach: Phase 1 → 2 → 3 → 4 → 5 → 6
- Single workflow for all users
- Archived in archive/v2.0/ for historical reference

---

## Version Notes

### About v0.0.1 (Initial Release)
This is the first public release of the Modular QGen Framework. The framework has been validated through real implementation (Evolution QTI project with 72 questions), but is still in early-stage development.

**What's stable:**
- Core 6-component architecture
- 5 workflow patterns
- Component documentation
- QTI specification format

**What's evolving:**
- Additional examples and case studies
- Refinement based on user feedback
- Expansion of workflow-specific guidance
- Extraction of Components 3, 5, 6 into separate files

**Feedback welcome!** Please share your experience using the framework.

---

## Upcoming in v0.1.0
- Complete extraction of all 6 components into separate files
- Additional workflow walkthroughs (2-3 more case studies)
- Visual workflow decision tree
- FAQ section based on user questions
- Troubleshooting guide

---

**For questions or suggestions, please open an issue on GitHub.**
