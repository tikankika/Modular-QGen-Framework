# Changelog

All notable changes to Modular QGen Framework are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### 2025-11-13 - MQG_0.2: BB6 Tags Architecture & Question Naming Documentation Update

#### Changed
- **MQG_bb6_Field_Requirements_v03.md** - Major updates to Tags structure and Question Name specification
  - **Added Question Name Section** (lines 10-32): Documented recommended practice of adding descriptive headings to questions
    - **Format**: `# Question N: Descriptive Name` before metadata section
    - **Examples**: `# Question 1: Prokaryot vs Eukaryot grundskillnad`, `# Question 5: DNA-replikation i S-fasen`
    - **Purpose**: Improves readability and organization of question banks
    - **Source**: Best practice observed in `BIOLOGI_QUIZ_Cell_Virus_v8.1_FINAL.md`

  - **Restructured Tags Section** (lines 106-188): Complete rewrite of tagging architecture
    - **OLD APPROACH**: Required LO codes (LO-01, LO-02, etc.) in Tags field
    - **NEW APPROACH**: Two-category tag structure for better searchability
      1. **Question-Specific Subject Words** (3-5 per question): Concrete topic words users can search for
         - Biology examples: Prokaryot, Eukaryot, DNA-replikation, Mitos, Meios, Cellkärna
         - Engineering examples: Well-to-Wheel, Fossil-fuels, Carbon-emissions
      2. **Structural Tags** (consistent across questions): Course ID, Bloom's Level, Difficulty, Type, Grading, Status
    - **Removed**: LO code requirements from Tags field
    - **Clarified**: Learning Objectives mapping tracked separately via BB2 Assessment Blueprint
    - **Added**: 8 complete examples showing good vs bad tagging practices
    - **Warning Added**: "LO codes are NOT searchable tags - use subject-specific keywords instead"
    - **Rationale**: LO codes (LO-01, LO-02) are classification codes, not searchable keywords

- **MQG_bb6_Output_Validation_v03.md** - Aligned validation rules with new Tags architecture
  - **Updated Tags Field Validation** (lines 165-231):
    - **Removed**: "✓ Learning Objective code(s)" requirement
    - **Added**: "✓ 3-5 Subject-Specific Keywords" requirement
    - **Added**: Warning for LO codes in Tags: "Tags contains LO code(s): {codes}. LO codes should NOT be in Tags - they are not searchable."
    - **Updated**: All examples to show subject-specific words (Prokaryot, DNA-replikation) instead of LO codes
  - **Updated Required Fields List** (lines 64-78):
    - **Removed**: "4. **Learning Objectives**: check presence" from required fields
    - **Added**: Note explaining LO mapping is tracked via BB2 Blueprint, not in question metadata
    - **Updated**: Tags field requirement to include "check subject-specific keywords (3-5 minimum)"
  - **Updated Example Errors** (line 813): Changed from "Missing required field 'Learning Objectives'" to "Missing required field 'Tags'"
  - **Updated Improvement Suggestions** (line 852): Changed from LO documentation reminder to Tags quality check

#### Impact
- **Improved Searchability**: Questions now tagged with concrete subject words instead of abstract LO codes
- **Better Organization**: Question Names provide quick overview of question bank contents
- **Clearer Separation**: LO mapping (classification) vs Tags (searchability) purposes now distinct
- **Documentation Alignment**: Requirements and validation docs now consistent with best practices

#### Files Updated
- `/docs/MQG_0.2/MQG_bb6_Field_Requirements_v03.md`
- `/docs/MQG_0.2/MQG_bb6_Output_Validation_v03.md`

---

### 2025-11-13 - MQG_0.2: BIOG001X Genetics Quiz Format Troubleshooting

#### Fixed
- **Text Entry Question Format Issues** - Identified and resolved markdown format errors in genetics quiz
  - **Issue 1 - Missing YAML Frontmatter**: File started with markdown heading instead of required YAML metadata
    - **Error**: "No YAML frontmatter found" + "Question block 1 returned no data"
    - **Cause**: Known parser regression (per QTI Generator CHANGELOG 2025-11-10)
    - **Fix**: Added complete YAML frontmatter with test_metadata, assessment_configuration, and learning_objectives
  - **Issue 2 - Text Entry Question Missing Blank Placeholder**: Question 2 (BIOG_GEN_TE_Q002) failed generation
    - **Error**: "Text entry question requires blanks definition" + question type "unknown"
    - **Cause**: Missing `{{BLANK-1}}` placeholder in question text (line 47)
    - **Spec**: Per markdown_specification.md lines 804-913, text_entry requires placeholders
    - **Fix**: Changed "Under vilken fas i cellcykeln kopieras DNA:t?" → "...DNA:t? Svar: {{BLANK-1}}"
  - **Issue 3 - Incorrect Blank Section Format**: Wrong markdown structure for blank definitions
    - **Current Format**: `## Blank 1` with bullet list under "Accepted Alternatives:"
    - **Required Format**: `## Blanks` → `### Blank 1` with structured fields
    - **Missing Fields**: **Correct Answer**, **Case Sensitive**, **Expected Length**
    - **Wrong Format**: Alternatives should be comma-separated, not bullet list
    - **Fix**: Restructured to match specification (lines 856-868 of markdown_specification.md)

#### Analysis
- **Root Cause**: Questions created without YAML frontmatter trigger parser regression
- **Impact**: 50-question bank failed at step 4 (XML generation) on question 2/50
- **Validation**: Step 1 passed incorrectly (should have caught missing frontmatter)
- **Resolution Status**: YAML added, Question 2 partially fixed (blank format pending)
- **Remaining Work**: Complete blank format fix + verify all other text_entry questions

#### Files Investigated
- Target: `50_Fragor_Genetik_BB6_FINAL (2).md` (BIOG001X genetics bank)
- Reference: QTI-Generator-for-Inspera `docs/markdown_specification.md`
- Reference: QTI-Generator-for-Inspera `CHANGELOG.md` (parser regression entry 2025-11-10)

#### Documentation Impact
- Confirms importance of YAML frontmatter requirement in BB6 specifications
- Validates text_entry format requirements in MQG_bb6_Field_Requirements_v03.md
- Highlights need for stricter step 1 validation (should catch missing frontmatter)

---

### 2025-11-09 - MQG_0.2: BB6 Hotspot Coordinate Format Documentation

#### Changed
- **MQG_bb6_Field_Requirements_v03.md** - Enhanced hotspot coordinate specification
  - Documented all 3 rectangle coordinate formats (lines 550-589):
    1. Corner coordinates: `x1=N, y1=N, x2=N, y2=N`
    2. Position + dimensions: `x=N, y=N, width=N, height=N`
    3. Plain format: `x1,y1,x2,y2`
  - Documented both circle coordinate formats:
    1. Named format: `x=N, y=N, radius=N`
    2. Plain format: `cx,cy,r`
  - Added shape name equivalence: "rectangle" and "rect" are accepted as equivalent
  - Added coordinate format conversion details
  - Added examples showing all valid formats
  - **Rationale**: QTI Generator parser now supports multiple coordinate formats for improved usability

- **MQG_bb6_Output_Validation_v03.md** - Comprehensive hotspot validation section rewrite
  - Completely rewrote hotspot validation section (lines 483-593)
  - Added detailed validation rules for all coordinate formats
  - Added shape name flexibility documentation (both "rect" and "rectangle" accepted)
  - Added coordinate validation rules:
    - Rectangle: Verify 4 values present and x2 > x1, y2 > y1
    - Circle: Verify 3 values present and radius > 0
  - Added 5 concrete examples showing different valid hotspot formats
  - Added comprehensive error message templates for each validation failure
  - Added step-by-step validation logic
  - **Purpose**: Align validation documentation with QTI Generator parser capabilities

#### Impact
- **Specification Completeness**: All coordinate formats accepted by QTI Generator now documented
- **Validation Accuracy**: Validation rules match parser implementation exactly
- **Usability**: Question authors have clear guidance on all acceptable formats
- **Consistency**: Documentation synchronized with QTI Generator implementation

#### Files Changed
- Updated: `docs/MQG_0.2/MQG_bb6_Field_Requirements_v03.md` (hotspot section lines 550-589)
- Updated: `docs/MQG_0.2/MQG_bb6_Output_Validation_v03.md` (hotspot section lines 483-593)

#### Integration with QTI Generator
- Documentation changes reflect QTI Generator fixes in session 2025-11-09
- Parser now supports x/y/width/height format in addition to x1/y1/x2/y2
- Parser accepts both "rect" and "rectangle" as equivalent shape names
- Validation script enhanced with `validate_hotspot_structure()` function
- See QTI-Generator-for-Inspera CHANGELOG.md (2025-11-09 Session 9) for implementation details

---

### 2025-11-08 - MQG_0.2 Branch: BB6 Restructuring to 2-Document System

#### Changed
- **BB6 Major Restructuring** - Simplified from 4-way split to 2-document system
  - **Rationale**: 4-way split (bb6a/b/c/d) created confusion for Claude Desktop
  - **New Approach**: Functional separation - field specs vs validation analysis
  - **Output Format Clarified**: Single markdown file with embedded metadata headers (not two-file system)

- **MQG_bb6_Field_Requirements_v03.md** (NEW - comprehensive field specification)
  - Purpose: Complete field specification for question generation
  - **Simplified Metadata Structure**: Type, Identifier, Points, Tags, Language (optional)
  - **Tags Enhancement**: LO codes, Bloom's Level, and Difficulty specified ONLY in Tags field
  - All 16 question type specifications with required sections
  - Inspera unified feedback requirement documentation
  - Format rules and validation priorities
  - Quick reference table for all question types
  - Optional configuration fields documented
  - Machine-readable, condensed format optimized for Claude Desktop

- **MQG_bb6_Output_Validation_v03.md** (NEW - validation and analysis guide)
  - Purpose: Validate and improve question output files from bb1-5 process
  - Step-by-step validation workflow
  - Metadata field validation rules
  - **Tags Validation**: Enforces LO/Bloom/Difficulty within Tags field
  - Question content validation
  - Type-specific validation checklists
  - Common errors with specific fix templates
  - Validation report format specification
  - Improvement suggestion framework
  - Designed for Claude Desktop to analyze output files and suggest improvements

- **Metadata Simplification** - Aligned with QTI Generator implementation
  - **Removed separate fields**: Learning Objectives, Bloom's Level, Difficulty
  - **Rationale**: These fields are NOT exported to QTI XML (only Tags field is exported)
  - **New approach**: All pedagogical metadata goes in Tags field
  - **Aligns with**: bb6b v02 decision and QTI Generator qti_packager.py implementation
  - **Evidence**: QTI Generator code explicitly states it does NOT export these fields
  - **Benefit**: Simpler structure, no redundant validation, matches actual QTI export behavior
  - **Tags structure**: Course ID, LO codes, Bloom's Level, Difficulty, topics, type, grading, status
  - **Example**: `TRA265, L1b, AY2024-25, Well-to-Wheel, LO1, Remember, Easy, Fill-Blank, Auto-Scored, Validated`

#### Removed
- **Archived 4-way split** - Moved to `docs/ModularQGen_archive/bb6_4way_split_archived_20251108/`
  - MQG_bb6a_Question_Output_Specifications_02.md
  - MQG_bb6b_Metadata_Requirements_02.md
  - MQG_bb6c_Validation_Checklist_02.md
  - MQG_bb6d_Output_File_Structure_02.md
  - Reason: Overly granular split created confusion; 2-document system provides clearer separation of concerns

#### Impact
- **Clearer Purpose Separation** - Field requirements vs output validation
  - bb6_Field_Requirements: "What to generate" (specification for question creation)
  - bb6_Output_Validation: "How to validate" (analysis guide for quality control)
- **Simplified Mental Model** - Easier for Claude Desktop to understand which document to use when
- **Output Format Clarity** - Single markdown file with embedded metadata (matches existing TRA265 example)
- **Better Usability** - Two comprehensive documents instead of four fragmented specs
- **Maintained Completeness** - All content from 4-way split retained and reorganized

#### Files Changed
- Created: `docs/MQG_0.2/MQG_bb6_Field_Requirements_v03.md`
- Created: `docs/MQG_0.2/MQG_bb6_Output_Validation_v03.md`
- Archived: `docs/ModularQGen_archive/bb6_4way_split_archived_20251108/` (bb6a, bb6b, bb6c, bb6d)
- Updated: `CHANGELOG.md` (this file)

---

### 2025-11-08 - MQG_0.2 Branch: BB6 Modular Split (ARCHIVED)

#### Added
- **MQG_0.2 Development Branch** - Created new branch for modular documentation development
  - Branch: MQG_0.2 (pushed to GitHub)
  - Purpose: Refine processes through modular building blocks
  - Location: `docs/MQG_0.2/`

- **BB6 4-Way Split** - Refactored BB6_v02 into four machine-readable documents
  - **MQG_bb6a_Question_Output_Specifications_02.md** (693 lines)
    - Question structure specifications for all 16 question types
    - Condensed technical format without examples or pedagogical content
    - Type codes, required sections, rules, forbidden sections
    - Quick reference table for rapid lookup
    - Decision rule for blank-type questions
    - Inspera unified feedback requirement

  - **MQG_bb6b_Metadata_Requirements_02.md** (143 lines)
    - Required fields: Type, Identifier, Points, Language, Tags
    - Removed unused fields: Learning_Objectives, Blooms_Level, Difficulty
    - Format specifications and accepted values
    - Answer field format rules
    - QTI language normalization (en → en_us, sv → sv_se, etc.)

  - **MQG_bb6c_Validation_Checklist_02.md** (387 lines)
    - Pre-QTI export validation workflow
    - Universal validation rules for all questions
    - Type-specific validation checklists
    - Common errors table
    - Validation severity levels

  - **MQG_bb6d_Output_File_Structure_02.md** (NEW - 344 lines)
    - Two-file output system: questions.md + metadata.csv/md
    - Separation of question content from metadata
    - CSV and Markdown metadata format options
    - Folder structure with images
    - Question-to-metadata linking via Question_Number
    - QTI Generator input expectations
    - Migration guide from single-file format
    - Complete example project structure

#### Changed
- **Documentation Format Philosophy** - Pivoted to machine-readable specifications
  - Target audience: Claude Desktop / GenAI (not human readers)
  - Format: Stringent, condensed, precise technical specs only
  - Removed: Emojis, examples, pedagogical explanations, fluff
  - Initial result: 1,834 lines → 1,151 lines (-37% reduction)
  - After QTI alignment: 1,223 lines (bb6a: 693, bb6b: 143, bb6c: 387)
  - After bb6d addition: 1,630 lines (bb6a: 694, bb6b: 144, bb6c: 388, bb6d: 404)
  - Net change: 1,834 → 1,630 lines (-11% reduction, +404 for two-file workflow)

- **Metadata Field Refinement (bb6b)** - Analysis of QTI Generator implementation
  - Removed fields not used in QTI export: Learning_Objectives, Blooms_Level, Difficulty
  - Made Language required (actually used in QTI XML: inspera:defaultLanguage)
  - Made Tags required (exported as searchable labels in IMS manifest)
  - Only fields that affect QTI output remain in specification
  - bb6b reduced from 181 → 143 lines (-21%)

- **Question Output Specification Refinement (bb6a)** - Aligned with QTI templates
  - **CRITICAL FIX:** Added Inspera unified feedback requirement
    - All feedback subsections (Correct/Incorrect/Partially Correct/Unanswered) receive identical content
    - Generator uses unified_feedback for all placeholders
    - Removed misleading "FEEDBACK_SUBSECTIONS" counts
    - Added comprehensive example showing unified feedback pattern
  - **Optional fields documented:**
    - Expected Length: default 15 (text_entry, fill_in_the_blank)
    - Prompt: default "Select all that apply" (multiple_response)
    - Scoring fields: intelligent defaults documented
    - Configuration fields: shuffle, editor_prompt, upload_prompt, field_width, hotspot coloring
  - **Implementation notes added:**
    - fill_in_the_blank uses text_entry template internally
    - true_false labels auto-generated from Language field
  - **Quick Reference Table updated:**
    - Removed obsolete "Partial Feedback" column
    - Added unified feedback note
  - **New section:** Optional Configuration Fields (common + type-specific)
  - bb6a increased 621 → 693 lines (+12% for critical clarifications)

#### Impact
- **Modular Architecture** - BB6 now separated by concern
  - bb6a: What to output (question structure)
  - bb6b: What metadata to include (field specs)
  - bb6c: How to validate (quality control)
  - bb6d: How to organize output files (two-file system)
- **Improved Maintainability** - Easier to update individual components
- **Optimized for GenAI** - Faster parsing, reduced token usage
- **Clear Separation** - Content vs metadata vs validation vs file structure
- **Two-File Workflow** - Enables bulk metadata editing, cleaner collaboration

#### Files Changed
- Created: `docs/MQG_0.2/MQG_bb6a_Question_Output_Specifications_02.md`
- Created: `docs/MQG_0.2/MQG_bb6b_Metadata_Requirements_02.md`
- Created: `docs/MQG_0.2/MQG_bb6c_Validation_Checklist_02.md`
- Created: `docs/MQG_0.2/MQG_bb6d_Output_File_Structure_02.md` (NEW)
- Updated: All bb6 documents with cross-references to bb6d
- Branch: MQG_0.2 (new development branch)

---

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
