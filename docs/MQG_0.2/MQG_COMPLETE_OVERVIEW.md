# MQG 0.2 - COMPLETE FRAMEWORK OVERVIEW

**Modular Question Generation Framework**  
**Version:** 0.2  
**Date:** November 2025

---

## FRAMEWORK ARCHITECTURE

MQG consists of **6 Building Blocks** that can be combined flexibly depending on entry point and needs. Each building block contains modular sub-components that function as independent "LEGO blocks."

---

## BUILDING BLOCK 1: CONTENT ANALYSIS

**Purpose:** Analyze instructional materials to establish validated learning objectives

**Entry Point:** Instructional materials (lectures, slides, readings, transcripts)

**Output:** Validated learning objectives, content architecture, example catalog, misconception registry

**Duration:** 4-6 hours

### Files (8 total, ~1,737 lines):

**bb1a - Introduction & Framework** (149 lines)
- Framework principles
- Process overview
- Prerequisites
- Navigation guide
- File dependency checklist

**bb1b - Stage 0: Material Analysis** (247 lines)
- AI independent analysis (60-90 min)
- Emphasis pattern identification
- Tier structure (1-4)
- Preliminary content architecture
- STAGE GATE: STOP before Stage 1

**bb1c - Stage 1: Initial Validation** (173 lines)
- Validation dialogue
- Correct Stage 0 findings
- Handle major misalignment
- STAGE GATE: STOP before Stage 2

**bb1d - Stage 2: Emphasis Refinement** (222 lines)
- Deep dive into content priorities
- Pedagogical rationale exploration
- Topic progression strategy
- STAGE GATE: STOP before Stage 3

**bb1e - Stage 3: Example Catalog** (190 lines)
- Document instructional examples
- 15-25 examples total
- Quality over quantity
- STAGE GATE: STOP before Stage 4

**bb1f - Stage 4: Misconception Analysis** (206 lines)
- Document common student errors
- 8-15 misconceptions total
- Systematic error focus
- STAGE GATE: STOP before Stage 5

**bb1g - Stage 5: Scope & Learning Objectives** (403 lines)
- Finalize scope boundaries
- Synthesize learning objectives (15-30 total)
- Bloom's taxonomy mapping
- Final BB1 output package
- STAGE GATE: STOP before BB2

**bb1h - Facilitation Best Practices** (147 lines)
- Dialogue facilitation principles
- Common pitfalls and solutions
- Cross-cutting guidance

---

## BUILDING BLOCK 2: ASSESSMENT DESIGN

**Purpose:** Design comprehensive assessment blueprint based on validated objectives

**Entry Point:** BB1 outputs OR existing learning objectives

**Output:** Complete assessment blueprint with question distribution

**Duration:** 1.5-2.5 hours

### Files (9 total):

**bb2a - Introduction & Foundations**
- Theoretical framework
- Process architecture
- Entry points
- Cross-references to bb2e (Bloom's) and bb2f (Question types)

**bb2b - Stage 1: Objective Validation**
- Validate BB1 learning objectives
- Ensure Bloom's levels appropriate
- STAGE GATE: STOP before Stage 2

**bb2c - Stage 2: Strategy Definition**
- Formative vs. summative decisions
- Assessment constraints
- Context specification
- STAGE GATE: STOP before Stage 3

**bb2d - Stage 3: Question Target**
- Calculate total question count
- Weighted distribution by learning objectives
- Coverage-based framework
- STAGE GATE: STOP before Stage 4

**bb2e - Stage 4: Bloom's Distribution**
- Authoritative Bloom's taxonomy definitions
- Distribute questions across cognitive levels
- Context-appropriate patterns
- STAGE GATE: STOP before Stage 5

**bb2f - Stage 5: Question Type Mix**
- Authoritative question type descriptions (10 types)
- Map cognitive levels to question formats
- Balance affordances and constraints
- STAGE GATE: STOP before Stage 6

**bb2g - Stage 6: Difficulty Distribution**
- Define difficulty levels (Easy, Medium, Hard)
- Distribute across cognitive × difficulty matrix
- Point allocation framework
- STAGE GATE: STOP before Stage 7

**bb2h - Stage 7: Blueprint Construction**
- Synthesize all previous stages
- Create comprehensive blueprint (5 components)
- Validation framework
- Output ready for BB4
- STAGE GATE: STOP before BB3/BB4

**bb2i - Facilitation Best Practices**
- Meta-guidance for facilitation
- Troubleshooting scenarios
- Quality indicators

---

## BUILDING BLOCK 3: TECHNICAL SETUP

**Purpose:** Configure technical systems (Inspera LMS) for question generation

**Entry Point:** BB2 blueprint OR existing technical requirements

**Output:** Technical configuration package, metadata system, label system

**Duration:** 2-3 hours

### Files (7 total, ~970 lines):

**bb3a - Introduction & Foundations** (150 lines)
- Technical framework overview
- Prerequisites
- Process roadmap

**bb3b - Stage 1: Platform Orientation** (85 lines)
- Inspera LMS overview
- Question bank structure
- STAGE GATE: STOP before Stage 2

**bb3c - Stage 2: Metadata Configuration** (145 lines)
- Define metadata system
- Align with BB2 blueprint
- STAGE GATE: STOP before Stage 3

**bb3d - Stage 3: Label System Design** (150 lines)
- Create hierarchical label system
- Support filtering and organization
- STAGE GATE: STOP before Stage 4

**bb3e - Stage 4: Question Type Mapping** (115 lines)
- Map BB2 question types to Inspera formats
- Technical specifications
- STAGE GATE: STOP before Stage 5

**bb3f - Stage 5: Technical Validation** (140 lines)
- Validate all technical configurations
- Ensure BB2 alignment
- STAGE GATE: STOP before output

**bb3g - Output & Implementation** (185 lines)
- Complete technical package
- Implementation guidance
- Transition to BB4

---

## BUILDING BLOCK 4: QUESTION GENERATION

**Purpose:** Generate high-quality assessment questions based on blueprint

**Entry Point:** BB2 blueprint + BB3 technical setup OR existing question requirements

**Output:** Complete question bank with metadata

**Duration:** Variable (depends on question count)

### Files (5 total, ~2,445 lines):

**bb4a - Introduction & Principles** (290 lines)
- Three-stage generation model
- Teacher decision authority
- AI prohibited actions
- Quality principles

**bb4b - Stage 4A: Basic Generation** (440 lines)
- Initial question generation
- Focus on pedagogical content
- No technical formatting yet
- 9 detailed dialogue examples
- STAGE GATE: STOP before Stage 4B

**bb4c - Stage 4B: Distribution Review** (485 lines)
- Validate distribution against blueprint
- Identify gaps and imbalances
- Pedagogical validation before formatting
- Prevents wasted effort on wrong questions
- STAGE GATE: STOP before Stage 4C

**bb4d - Stage 4C: Finalization** (590 lines)
- Technical formatting (QTI, Inspera)
- Apply BB3 metadata and labels
- Final quality checks
- Export preparation
- STAGE GATE: STOP before BB5

**bb4e - Process Guidelines** (640 lines)
- Comprehensive facilitation guidance
- Question quality criteria
- Distractor development
- Troubleshooting scenarios

---

## BUILDING BLOCK 5: QUALITY ASSURANCE

**Purpose:** Systematic validation of generated questions

**Entry Point:** BB4 question bank OR existing questions

**Output:** Validated question bank, quality report, revision recommendations

**Duration:** Variable (depends on question count)

### Files (6 total, ~1,765 lines):

**bb5a - Introduction & Foundations** (165 lines)
- Four-phase validation model
- Quality framework
- Process overview

**bb5b - Phase 1: Automated Validation** (220 lines)
- Technical validation
- Distribution verification
- Metadata completeness
- PHASE GATE: STOP before Phase 2

**bb5c - Phase 2: Pedagogical Review** (310 lines)
- Content accuracy review
- Alignment with objectives
- Cognitive level verification
- PHASE GATE: STOP before Phase 3

**bb5d - Phase 3: Collective Analysis** (265 lines)
- Pattern analysis across question bank
- Balance and coverage assessment
- Difficulty progression review
- PHASE GATE: STOP before Phase 4

**bb5e - Phase 4: Documentation** (385 lines)
- Comprehensive quality report
- Revision recommendations
- Documentation of decisions
- PHASE GATE: STOP before output

**bb5f - Output & Transition** (420 lines)
- Final validated question bank
- Quality certification
- Transition to BB6

---

## BUILDING BLOCK 6: EXPORT & INTEGRATION

**Purpose:** Export validated questions to target systems

**Entry Point:** BB5 validated question bank

**Output:** System-ready question files (QTI, Inspera format)

**Duration:** 30 minutes - 1 hour

### Files (2 total):

**bb6 - Field Requirements**
- Technical field specifications
- QTI format requirements
- Inspera integration details

**bb6 - Output Validation**
- Export validation procedures
- Final quality checks
- Integration testing

---

## FLEXIBLE ENTRY POINTS

### Full Process (Most Common):
BB1 → BB2 → BB3 → BB4 → BB5 → BB6

### With Existing Objectives:
BB2 → BB3 → BB4 → BB5 → BB6

### With Existing Blueprint:
BB3 → BB4 → BB5 → BB6

### Question Revision Only:
BB5 → (revise with BB4) → BB5 → BB6

### Technical Setup Only:
BB3 (independent)

---

## MODULAR "LEGO BLOCK" STRUCTURE

### Within Each Building Block:

Each building block consists of modular sub-components (bb1a, bb1b, bb1c, etc.) that:

1. **Can be used independently** - Each file is self-contained
2. **Reference each other clearly** - Cross-references explicit
3. **Have distinct purposes** - No duplication
4. **Follow consistent patterns** - Similar structure across BBs

### Between Building Blocks:

Building blocks can be:

1. **Combined sequentially** - BB1 → BB2 → BB3 → BB4 → BB5 → BB6
2. **Used independently** - Start with BB2 if objectives exist
3. **Iterated** - Return to earlier blocks for refinement
4. **Skipped** - Use only relevant blocks for specific needs

---

## STAGE GATE SYSTEM

**Critical Safety Feature:**

Every stage and phase in BB1-BB5 includes **STAGE GATES** that:

1. **STOP** - Claude stops automatically at stage completion
2. **WAIT** - Explicit teacher approval required to proceed
3. **CHECK** - Verify next stage file loaded before continuing
4. **PREVENT** - No improvisation without instructions

**Purpose:** Teacher maintains full control over pacing and decisions

---

## FILE ORGANIZATION

**Total Framework Files:** 41

- **BB1:** 8 files (~1,737 lines)
- **BB2:** 9 files
- **BB3:** 7 files (~970 lines)
- **BB4:** 5 files (~2,445 lines)
- **BB5:** 6 files (~1,765 lines)
- **BB6:** 2 files
- **Summaries:** 4 files

**Total Documentation:** ~7,000+ lines

**Average File Size:** 170-500 lines (manageable, focused)

---

## QUALITY INDICATORS

**Framework Maturity:**
- BB1: Mature, overlap-refined (4 of 8 files)
- BB2: Split complete, needs overlap analysis
- BB3: Split complete, needs overlap analysis
- BB4: Newly split, comprehensive
- BB5: Newly split, detailed
- BB6: Exists, needs enhancement review

**Design Quality:**
- Stage gates implemented: BB1, BB4, BB5
- Teacher authority emphasized: All BBs
- Modular structure: All BBs
- Cross-references clear: All BBs
- Dialogue examples: Extensive in BB4

---

## NAVIGATION TIPS

### For Users:

1. **Always start with 'a' file** (bb1a, bb2a, etc.) for introduction
2. **Follow stage sequence** within each building block
3. **Respect stage gates** - don't rush ahead
4. **Reference facilitation files** (bb1h, bb2i, bb4e) when stuck
5. **Use cross-references** - files point to related content

### For Claude (AI Facilitator):

1. **Never proceed without explicit approval** at stage gates
2. **Always check file availability** before starting a stage
3. **Reference authoritative definitions** (bb2e for Bloom's, bb2f for question types)
4. **Maintain teacher decision authority** - facilitate, don't decide
5. **Use dialogue examples** from bb4 as models

---

## FRAMEWORK PRINCIPLES

**1. Teacher Pedagogical Authority**
- Teacher makes all pedagogical decisions
- AI facilitates dialogue and executes tasks
- Explicit approval required at all decision points

**2. Systematic Structure**
- Sequential stages build on previous work
- No skipped steps
- Validation at each stage
- Clear dependencies

**3. Explicit Documentation**
- All decisions documented with rationale
- Complete audit trail
- Transparent methodology
- Reproducible process

**4. Flexibility and Adaptation**
- Multiple entry points supported
- Revision workflows included
- Context-sensitive recommendations
- Hybrid approaches allowed

**5. Quality Over Quantity**
- Selection criteria enforce focus
- Validation at multiple points
- Comprehensive quality assurance
- Continuous refinement

---

## SUCCESS METRICS

**Process Quality:**
- Teacher satisfaction with dialogue
- Clarity of decision points
- Efficiency of workflow
- Completeness of outputs

**Product Quality:**
- Alignment with objectives
- Distribution accuracy
- Question quality
- Technical correctness

**Framework Usability:**
- Time to completion
- Error rates
- Revision frequency
- User confidence

---

## FUTURE DEVELOPMENT

**Immediate:**
- Complete overlap analysis for all BB files
- Test complete framework with real materials
- Gather user feedback
- Refine based on practical use

**Short-term:**
- Integration with QTI generation tools
- Automated metadata generation
- Template libraries
- Example question banks

**Long-term:**
- Multi-language support
- Additional LMS integrations
- AI-assisted validation
- Research publication (AIED 2026)

---

**Document Purpose:** Complete Framework Overview  
**Intended Audience:** Teachers, AI facilitators, framework developers  
**Last Updated:** November 2025  
**Framework Version:** MQG 0.2
