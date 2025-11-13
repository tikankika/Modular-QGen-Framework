# BUILDING BLOCK 3d: STAGE 3 - LABEL SYSTEM DESIGN

**Component:** Building Block 3d  
**Framework:** Modular Question Generation System  
**Stage:** 3 of 5  
**Purpose:** Create searchable organizational structure through metadata labels

---

## STAGE 3: LABEL SYSTEM DESIGN

### Purpose

Stage 3 creates the organizational infrastructure through systematic label design. Effective labels balance granularity with usability, creating categories that support both current needs and future question bank growth.

Labels become searchable tags in the question bank interface, enabling discovery through multiple access paths: course, topic, cognitive level, learning objective, difficulty, etc.

---

## LABEL CATEGORIES

### Primary Classification (Required)

**Course Code:**
- Must match subject field from Stage 2
- Example: BIOG001X
- Applied to all questions

### Topic Categorization (2-4 labels recommended)

**Major Topic:**
- Broad content area
- Example: "evolution"

**Subtopics (1-3):**
- More specific content elements
- Example: "natural_selection", "genetic_drift"
- Balance specificity with usability

### Cognitive Level Indicators (Recommended)

**Include Bloom's taxonomy levels:**
- Remember
- Understand
- Apply
- Analyze
- Evaluate
- Create (if used)

Enables filtering questions by cognitive demand.

### Learning Objective Tags (Recommended)

**Include LO identifiers:**
- LO1, LO2, LO3, ..., LOn
- Matches IDs from Stage 2
- Enables finding all questions for specific objective

### Administrative Labels (As Needed)

**Development Status:**
- draft | review | ready
- Tracks question lifecycle

**Difficulty Level:**
- basic | intermediate | advanced
- Alternative to or supplement for Easy/Medium/Hard

**Special Markers:**
- calculation | diagram | scenario
- Indicates special content or format requirements

---

## LABEL FORMATTING RULES

**Consistency Requirements:**
- No prefixes: "LO1" not "LO:LO1" or "objective_LO1"
- Consistent capitalization (recommend lowercase for topics, proper case for levels)
- No special characters except hyphen (-) and underscore (_)
- Maximum 50 characters per label
- Use underscores for multi-word labels: "natural_selection" not "natural selection"

**Examples of Well-Formatted Labels:**
- BIOG001X
- evolution
- natural_selection
- Remember
- LO1
- intermediate
- calculation

**Examples of Poor Formatting:**
- BIOG001X: Evolution (contains colon)
- natural selection (contains space)
- LO: 1 (prefix and space)
- INTER-MEDIATE (unnecessary hyphenation)

---

## LABEL ARCHITECTURE EXAMPLE

For a biology question on natural selection application:

**Applied Labels:**
- BIOG001X (course)
- evolution (major topic)
- natural_selection (subtopic)
- Apply (cognitive level)
- LO3 (learning objective)
- intermediate (difficulty, if used)
- ready (status, if used)

This creates multiple access paths: filter by course, topic, cognitive level, objective, or difficulty.

---

## COMPLETE LABEL SET

### Standard Labels (Applied to All Questions)
- [course_code]

### Content Labels (Applied Based on Question Topic)
- [topic1]
- [topic2]
- [subtopic1]
- [subtopic2]
- [subtopic3]

### Cognitive Labels (Applied Based on Question Level)
- Remember | Understand | Apply | Analyze | Evaluate | Create

### Objective Labels (Applied Based on Question Assignment)
- LO1 | LO2 | LO3 | ... | LO[n]

### Optional Administrative Labels
- [status: draft/review/ready]
- [difficulty: basic/intermediate/advanced]
- [special markers: calculation/diagram/scenario]

---

## STAGE 3 COMPLETION CHECKPOINT

**This stage is now complete.**

### Completion Verification
- Primary classification (course code) defined
- Topic categorization established (2-4 labels)
- Cognitive level indicators decision made
- LO tag approach determined
- Optional administrative labels defined
- All labels follow formatting rules

**Status:** Complete when label system designed

**Next stage:** bb3e (Stage 4: Question Type Mapping)

---

**Document Status:** BB3 Stage 3 Complete  
**Component:** Building Block 3d  
**Previous File:** bb3c (Stage 2: Metadata Field Configuration)  
**Next File:** bb3e (Stage 4: Question Type Mapping)  
**Lines:** 150
