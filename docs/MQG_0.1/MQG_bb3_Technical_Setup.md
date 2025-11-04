# BUILDING BLOCK 3: TECHNICAL SETUP
## Metadata Configuration for Platform Compliance

**Component Type:** Building Block 3  
**Framework:** Modular Question Generation System  
**Classification:** 🔶 STATIC (checklist-driven compliance)  
**Primary Input:** Building Block 2 (Assessment Blueprint with Learning Objectives)  
**Primary Output:** Technical Metadata Configuration Document  
**Purpose:** Establish platform-compliant technical foundation for question generation  
**Estimated Duration:** 30 minutes

---

## OVERVIEW AND PURPOSE

Building Block 3 represents the technical translation layer between pedagogical design and platform implementation. This component transforms the assessment blueprint from Building Block 2 into a technical specification that ensures all generated questions will function properly within the target Learning Management System (LMS), with particular emphasis on Inspera's requirements.

The technical setup process operates through systematic compliance checking rather than pedagogical dialogue. Where Building Blocks 1 and 2 required teacher judgment and iterative refinement, Building Block 3 follows predetermined technical specifications that ensure platform compatibility. This static nature reflects the binary requirements of technical systems—metadata either complies with platform specifications or it does not.

Unlike the pedagogical focus of previous building blocks, Building Block 3 addresses fundamental technical questions: How will questions be organized in the question bank? What metadata enables efficient searching and filtering? Which technical formats support the desired question types? How do platform-specific constraints affect implementation?

The systematic nature of this building block ensures technical reliability while maintaining efficiency. Teachers provide required information through structured checklists, and the framework validates compliance against platform specifications. This approach prevents common technical errors that would otherwise emerge during question import or student assessment delivery.

---

## THEORETICAL FOUNDATIONS

### Technical Interoperability in Educational Systems

Building Block 3 operationalizes principles of technical interoperability as defined by the IMS Global Learning Consortium standards, particularly QTI 2.2 (Question and Test Interoperability). These standards ensure that assessment content can move between compliant systems while preserving both content and metadata integrity.

Technical metadata serves multiple functions beyond mere compliance. Vollmer (2018) identifies three critical roles of educational metadata: discovery (finding appropriate content), administration (managing content lifecycle), and pedagogy (supporting instructional decisions). Building Block 3 addresses all three dimensions through systematic metadata configuration.

### Metadata as Organizational Infrastructure

The label system implemented in Building Block 3 creates what Star and Ruhleder (1996) term "information infrastructure"—invisible support systems that enable visible work. In the context of question banks, metadata labels function as the organizational infrastructure that makes large collections of questions manageable and useful.

Effective metadata design follows established principles from information science. Greenberg (2005) emphasizes that metadata should be purposeful (serving identified needs), practical (feasible to implement), and principled (following consistent rules). Building Block 3 operationalizes these principles through structured label categories that support both immediate filtering needs and long-term question bank maintenance.

### Platform Constraints as Design Parameters

Technical platforms impose what Norman (2013) calls "forcing functions"—physical or logical constraints that guide user behavior. In assessment systems, these constraints include character limits, required fields, and standardized vocabularies. Building Block 3 transforms these constraints from obstacles into design parameters that ensure reliable system behavior.

The static nature of this building block reflects the deterministic requirements of technical systems. Unlike pedagogical decisions that benefit from dialogue and iteration, technical specifications require compliance with predetermined standards. This distinction drives the checklist-based approach that characterizes Building Block 3.

---

## PROCESS ARCHITECTURE

### Entry Requirements and Prerequisites

Building Block 3 requires specific inputs to proceed effectively:

**Primary Requirement:** Completed Assessment Blueprint from Building Block 2, including:
- Defined learning objectives with unique identifiers
- Selected question types from the blueprint
- Assessment configuration (formative/summative, feedback timing)
- Language specification for the assessment

**Secondary Requirements:** Basic technical information about the target platform:
- LMS platform name (Inspera, Canvas, Moodle, etc.)
- Course identifier or code
- Any institution-specific metadata requirements

**Optional Inputs:** Existing technical specifications from previous assessments:
- Previous metadata configurations for reference
- Established label conventions within the institution
- Department or program-specific requirements

Without validated learning objectives from Building Block 2, metadata configuration cannot establish the necessary connections between questions and learning goals. The technical setup depends on pedagogical decisions being finalized before technical implementation begins.

### Process Overview: Five Systematic Stages

Building Block 3 follows a structured five-stage process that transforms pedagogical specifications into technical configurations. Each stage involves compliance checking against platform requirements, with validation steps ensuring technical accuracy.

The stages progress from understanding platform requirements to producing validated technical specifications:

1. **Platform Orientation** establishes understanding of system requirements
2. **Metadata Field Configuration** captures required technical information
3. **Label System Design** creates searchable organizational structure
4. **Question Type Mapping** connects pedagogical types to technical codes
5. **Technical Validation** confirms compliance and completeness

### Stage 1: Platform Orientation

The process begins with systematic review of platform-specific requirements and constraints. This orientation ensures shared understanding of technical terminology and system behavior.

```
PLATFORM ORIENTATION CHECKLIST

Target Platform: [Inspera / Canvas / Other: ________]

Understanding Confirmation:
□ Metadata vs. content distinction clear
□ Label system purpose understood
□ Question type codes reviewed
□ Import/export process familiar
□ Character limits and constraints noted

Platform-Specific Notes:
[Document any special requirements or institutional customizations]
```

For Inspera specifically, critical orientations include understanding that labels become searchable tags in the question bank interface, that certain metadata appears only in manifest files rather than individual questions, and that question type codes must match exactly the platform's predetermined values.

### Stage 2: Metadata Field Configuration

Stage 2 systematically collects required metadata values through structured checklists. Each field serves specific functions in the platform ecosystem.

```
REQUIRED METADATA CONFIGURATION

Assessment Identification:
□ title: _________________________________
  (Descriptive name visible in question bank)
  
□ identifier: _____________________________
  Format: COURSE_TOPIC_VERSION
  Example: BIOG001X_evolution_v2
  
□ language: _____
  ISO 639-1 code: en | sv | no | da | de | fr
  Must match question content language

Course Classification:
□ subject: _______________
  (Course code, becomes primary search label)
  
□ academic_level: _______________
  undergraduate | graduate | professional
  
□ academic_year: _____
  (Current academic year)

Learning Objectives Mapping:
Total objectives from BB2: ____

□ All objectives have unique IDs (LO1, LO2, etc.)
□ All objectives have clear descriptions
□ Mapping table created for question assignment

Assessment Configuration:
□ type: [formative | summative]
  (From BB2 assessment strategy)
  
□ feedback_mode: [immediate | deferred | none]
  (Determines when students see results)
  
□ duration_minutes: _____
  (If timed assessment)
  
□ attempts_allowed: _____
  (Number of permitted attempts)
```

Each field connects directly to platform functionality. The title appears in question lists, the identifier ensures uniqueness across the system, and the language code determines interface localization. These technical details, while seemingly minor, significantly impact system usability.

### Stage 3: Label System Design

Stage 3 creates the organizational infrastructure through systematic label design. Effective labels balance granularity with usability, creating categories that support both current needs and future question bank growth.

```
LABEL SYSTEM DESIGN

Primary Classification (Required):
□ Course code: ____________
  (Must match subject field above)

Topic Categorization (2-4 labels):
□ Major topic: _______________________
□ Subtopic 1: _______________________
□ Subtopic 2: _______________________
□ Additional: _______________________

Cognitive Level Indicators (Optional but Recommended):
□ Include Bloom's taxonomy levels: Yes | No
  If yes: Remember | Understand | Apply | 
          Analyze | Evaluate | Create

Learning Objective Tags (Optional but Recommended):
□ Include LO identifiers: Yes | No
  If yes: LO1 | LO2 | LO3 | ... | LO[n]

Administrative Labels (As Needed):
□ Development status: _________________
  Examples: ready | review | draft
□ Difficulty level: __________________
  Examples: basic | intermediate | advanced
□ Special markers: ___________________
  Examples: calculation | diagram | scenario

Label Formatting Rules Applied:
□ No prefixes (correct: "LO1" not "LO:LO1")
□ Consistent capitalization
□ No special characters (except - and _)
□ Maximum 50 characters per label
□ Matches existing institutional conventions
```

The label system creates multiple access paths to questions. A single question about natural selection might carry labels "BIOG001X", "evolution", "natural_selection", "Apply", and "LO3", enabling discovery through course, topic, concept, cognitive level, or learning objective searches.

### Stage 4: Question Type Mapping

Stage 4 translates pedagogical question types from the assessment blueprint into platform-specific technical codes. This mapping ensures that question functionality matches instructional intent.

```
QUESTION TYPE TECHNICAL MAPPING

From Assessment Blueprint:
Total question types in use: ____

Mapping Verification:
□ Multiple Choice → multiple_choice_single
□ Multiple Response → multiple_response  
□ True/False → true_false
□ Text Entry → text_entry
□ Numeric Entry → numeric
□ Essay/Text Area → text_area
□ Extended Text → extended_text
□ Fill in Blank → fib_text
□ Matching → match
□ Ordering → order
□ Hotspot → hotspot
□ File Upload → file_upload

Platform-Specific Validations:
□ All selected types supported by platform
□ Special configuration needs identified
□ Scoring implications understood
□ Student interface implications reviewed

Technical Constraints Noted:
[Document any limitations or special requirements]
```

Accurate type mapping prevents functional mismatches. For instance, mapping a multiple response question (where multiple answers can be correct) to a single choice type would fundamentally alter the assessment's validity.

### Stage 5: Technical Validation

Stage 5 performs systematic validation of all technical configurations before proceeding to question generation. This validation prevents downstream errors that would be costly to correct after questions are written.

```
TECHNICAL VALIDATION CHECKLIST

Completeness Validation:
□ All required fields populated
□ All learning objectives mapped
□ All question types mapped
□ Label system comprehensive

Consistency Validation:
□ Identifier unique (no conflicts)
□ Language code matches content
□ Subject matches course code label
□ Question types match blueprint

Compliance Validation:
□ Character limits respected
□ Required formats followed
□ Platform constraints satisfied
□ Institutional requirements met

Cross-Reference Validation:
□ LO count matches BB2 output
□ Question types match BB2 blueprint
□ Assessment config matches BB2 strategy
□ Language matches instructional context

VALIDATION RESULT: [PASS | REVISE]

If REVISE, specific issues:
_____________________________________
_____________________________________
```

Only after successful validation does the technical configuration become final. This systematic approach prevents the frustration of discovering technical incompatibilities after significant question development effort.

---

## OUTPUT STRUCTURE

### Technical Configuration Document Format

Building Block 3 produces a comprehensive Technical Configuration Document that serves as the authoritative reference for all technical aspects of question generation:

```markdown
# Technical Configuration: [Topic] ([Course])

## Platform Specifications
**Target LMS:** [Platform Name]  
**Import Format:** QTI 2.2  
**Language:** [ISO Code]  
**Generated:** [Date]  
**Status:** VALIDATED

## Assessment Metadata

### Core Identification
- **Title:** [Descriptive title]
- **Identifier:** [Unique identifier]
- **Subject:** [Course code]
- **Language:** [ISO code]
- **Academic Level:** [Level]
- **Academic Year:** [Year]

### Assessment Configuration
- **Type:** [formative/summative]
- **Feedback Mode:** [immediate/deferred/none]
- **Duration:** [X minutes or unlimited]
- **Attempts:** [Number or unlimited]

## Learning Objectives Registry

Total Objectives: [N]

| ID | Description | Questions |
|----|-------------|-----------|
| LO1 | [Objective text] | TBD |
| LO2 | [Objective text] | TBD |
| ... | ... | ... |
| LO[n] | [Objective text] | TBD |

## Label Architecture

### Primary Classification
- Course: [COURSE_CODE]

### Topic Hierarchy
- Major Topic: [topic]
  - Subtopic: [subtopic1]
  - Subtopic: [subtopic2]

### Optional Categorizations
- Bloom's Levels: [Enabled/Disabled]
- LO Tags: [Enabled/Disabled]
- Difficulty Markers: [Enabled/Disabled]
- Status Indicators: [List if used]

### Complete Label Set
Standard labels applied to all questions:
[course_code]

Additional labels available for use:
[topic], [subtopic1], [subtopic2], [cognitive_levels], 
[LO1-LOn], [difficulty_levels], [status_markers]

## Question Type Specifications

### Approved Type Mappings
| Blueprint Type | Technical Code | Quantity | Auto-Score |
|---------------|----------------|----------|------------|
| [Type] | [technical_code] | [N] | [Yes/No] |
| ... | ... | ... | ... |

### Platform Constraints
[Document any specific limitations or requirements]

## Validation Confirmation

Technical Validation Status: **PASSED**
- ✓ All required fields complete
- ✓ Platform compliance verified
- ✓ Label system consistent
- ✓ Question types supported
- ✓ Cross-references validated

Configuration frozen at: [Timestamp]
Changes require formal revision process.

## Implementation Notes

### For Question Generation (Building Block 4)
- Use exact technical codes from mapping table
- Apply label architecture consistently
- Include all required metadata fields
- Reference LO IDs from registry

### For Quality Assurance (Building Block 5)
- Validate technical codes match specification
- Verify label consistency
- Confirm metadata completeness
- Check platform compliance

### For Export/Integration (Building Block 6)
- Technical specifications ready for QTI generation
- Metadata structure validated for import
- Label system prepared for question bank
- All platform requirements satisfied

---

**Next Step:** Proceed to Building Block 4 (Question Generation)  
**Alternative:** Return to Building Block 2 if technical constraints require design revision
```

---

## TRANSITION PATHWAYS FROM BUILDING BLOCK 3

### Standard Path: Proceed to Building Block 4

Most implementations proceed directly from Building Block 3 to Building Block 4 (Question Generation):

```
Building Block 3 Complete → Building Block 4 (Question Generation)

Rationale for proceeding:
- Technical specifications validated and ready
- Metadata structure established
- Question type mappings confirmed
- Platform compliance verified

Building Block 3 outputs directly inform question generation:
- Writers use exact technical codes
- Apply predetermined label structure
- Include required metadata fields
- Follow platform constraints

This sequential path enables efficient question development with
technical confidence.
```

### Revision Path: Return to Building Block 2

Technical validation sometimes reveals constraints requiring design revision:

```
Building Block 3 Validation → Building Block 2 (Revision)

Reasons for returning to Building Block 2:
- Platform doesn't support planned question types
- Technical constraints conflict with assessment strategy  
- Metadata requirements affect question distribution
- Institutional policies require design changes

After Building Block 2 revision, return to Building Block 3 to update
technical configuration based on revised assessment blueprint.
```

### Alternative Path: Platform Migration

When moving existing questions to a new platform:

```
Building Block 3 (Platform A) → Building Block 3 (Platform B)

Migration considerations:
- Question type compatibility between platforms
- Metadata field mapping differences
- Label system translation needs
- Format conversion requirements

May require creating crosswalk documentation mapping Platform A
specifications to Platform B requirements.
```

---

## CRITICAL IMPLEMENTATION NOTES

### For Framework Implementation

The static nature of Building Block 3 requires different implementation patterns than dynamic building blocks. Compliance checking replaces pedagogical dialogue, and validation operates through systematic verification rather than iterative refinement. Technical specifications must be treated as authoritative once validated—ad hoc modifications risk system failures.

Platform-specific variations require modular configuration templates. While the process remains consistent, the specific fields, codes, and constraints vary significantly between Inspera, Canvas, Moodle, and other systems. Implementation must support platform-specific configurations while maintaining consistent process flow.

### For Instructor Users

Technical configuration may seem disconnected from pedagogical goals, but these specifications directly impact student experience. Clear labels improve question discovery for review. Proper metadata enables prerequisite checking. Correct question types ensure intended interactions. Time invested in technical setup pays dividends in system usability.

Common pitfall: attempting to skip or rush Building Block 3 to begin question writing immediately. This invariably leads to rework when technical incompatibilities emerge during import. The 30-minute investment in proper technical setup saves hours of debugging and reformatting later.

### For Technical Development

Building Block 3 must maintain current platform specifications as systems evolve. Regular updates ensure compatibility with platform changes. Version control for configuration templates enables rollback if platform updates introduce breaking changes.

Validation rules should be comprehensive but comprehensible. Cryptic error messages frustrate users and delay progress. Each validation check should clearly explain what failed and how to correct it. Consider progressive validation that identifies all issues simultaneously rather than failing on first error.

---

## SUMMARY

Building Block 3 establishes the technical foundation that enables successful question implementation in Learning Management Systems. Through systematic compliance checking and structured configuration, this component transforms pedagogical designs into technical specifications that ensure platform compatibility and system usability.

The static, checklist-driven nature of this building block reflects the deterministic requirements of technical systems. While pedagogical decisions benefit from dialogue and iteration, technical specifications require precision and compliance. This distinction drives both the process design and the validation approach that characterizes Building Block 3.

Successful completion of Building Block 3 provides question writers with clear technical specifications, validated metadata structures, and platform-compliant configurations. These outputs enable efficient question generation while preventing costly technical errors that would otherwise emerge during system implementation.

---

**Document Status:** Comprehensive Building Block Documentation  
**Version:** 1.0  
**Component Type:** Building Block 3  
**Framework:** Modular Question Generation System  
**Classification:** Static (Checklist-driven)  
**Theoretical Foundation:** Technical interoperability, information infrastructure, platform constraints