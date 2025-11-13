# BUILDING BLOCK 5: QUALITY ASSURANCE

**Component:** Building Block 5  
**Framework:** Modular Question Generation System  
**Classification:** 🔷🔶 HYBRID (automated validation + expert judgment)  
**Primary Input:** Building Block 4 (Generated Questions)  
**Primary Output:** Validated Question Set with QA Report  
**Purpose:** Ensure questions meet technical, pedagogical, and disciplinary standards  
**Estimated Duration:** 1-2 hours (40-50 questions)

---

## OVERVIEW

Building Block 5 validates generated questions through systematic multi-dimensional review combining automated technical checks with expert pedagogical judgment. This component ensures questions align with learning objectives, function technically in the target platform, maintain appropriate cognitive demands, and exhibit pedagogical soundness before deployment.

Quality assurance operates as a critical gate preventing deployment of assessments containing technical flaws, pedagogical misalignment, or disciplinary inaccuracies. The validation process examines both individual question quality and collective assessment coherence.

---

## VALIDATION PHASES

### Phase 1: Automated Technical Validation

**Purpose:** Verify structural correctness and platform compliance

**Automated Checks:**

**Format Compliance:**
- Correct markdown structure
- Required sections present
- Proper element nesting

**Metadata Validation:**
- All required fields populated
- Learning objective IDs match BB2
- Bloom's levels use approved vocabulary
- Question types match QTI formats
- Difficulty levels valid
- Point values within range
- Identifiers unique

**QTI Compliance:**
- Question structures convert to QTI
- Metadata maps to QTI elements
- No conversion-blocking elements

**Cross-Reference Validation:**
- Learning objectives exist in blueprint
- Bloom's levels align with objectives
- Question types match metadata

**Quality Indicators (flagged for expert review):**
- Reading level analysis
- Language complexity metrics
- Structural anomalies
- Potential bias terms

**Output:** Technical validation report identifying:
- Critical errors (must fix)
- Warnings (recommended fixes)
- Quality flags (expert review needed)

**Status:** PASS required before Phase 2

### Phase 2: Pedagogical Quality Review

**Purpose:** Expert evaluation of teaching effectiveness and disciplinary accuracy

**Review Dimensions:**

**Alignment Verification:**
- Does question assess specified learning objective?
- Can students answer correctly without objective mastery?
- Does context match authentic application?

**Cognitive Demand Validation:**
- Does question require claimed Bloom's level?
- Could students answer using lower-level processes?
- Is cognitive demand appropriate for objective?

**Difficulty Calibration:**
- Easy: 80-95% prepared students succeed
- Medium: 60-79% succeed
- Hard: 40-59% succeed
- Does difficulty match actual cognitive demand?

**Disciplinary Accuracy:**
- Factually correct content
- Current understanding (not outdated)
- Correct terminology usage
- Authentic scenarios

**Language Clarity:**
- Unambiguous task presentation
- Appropriate vocabulary for students
- Clear sentence structure
- No unnecessary complexity

**Distractor Quality** (selected-response):
- Represent plausible alternatives
- Reflect common misconceptions
- Similar length to correct answer
- No obvious mismatches

**Constructed-Response Rubrics:**
- Clear scoring criteria
- Complete/partial credit defined
- Examples at different score levels
- Consistent scoring guidance

**Feedback Quality:**
- Explains why answers correct/incorrect
- Connects to underlying concepts
- Addresses misconceptions
- Instructional rather than judgmental

**Accessibility Review:**
- Language appropriate for non-native speakers
- No unnecessary cultural references
- Format accessible for disabilities
- No stereotyping or exclusions

**Review Decision per Question:**
- **APPROVE:** Meets quality standards
- **APPROVE WITH NOTES:** Acceptable, note future improvements
- **REVISE REQUIRED:** Specific revisions needed before approval
- **REJECT:** Fundamental problems, requires regeneration

### Phase 3: Collective Assessment Analysis

**Purpose:** Evaluate complete question set as coherent instrument

**Coverage Validation:**
- Every learning objective has minimum coverage (≥2 questions)
- Tier 1 (essential) objectives adequately covered
- Tier 2 (important) objectives represented
- No systematic gaps

**Distribution Validation:**

**Bloom's Cognitive Levels:**
- Actual vs. blueprint distribution
- Within tolerance (±5%)
- Cognitive emphasis matches intent

**Question Types:**
- Actual vs. blueprint distribution
- Adequate format variety
- Supports construct representation

**Difficulty Levels:**
- Actual vs. blueprint distribution
- Appropriate challenge distribution
- Avoids floor/ceiling effects

**Consistency Checks:**
- Terminology consistent across questions
- No question dependencies
- No excessive redundancy
- Point allocation proportional

**Assessment Character:**
- Matches intended purpose (formative/summative)
- Appropriate cognitive emphasis
- Suitable difficulty profile
- Reasonable time requirements

**Collective Status:**
- **PASS:** Coverage complete, distributions validated
- **ADJUSTMENTS:** Minor resequencing/point changes
- **ADDITIONAL GENERATION:** Coverage gaps or distribution imbalances
- **MAJOR REVISION:** Systematic problems requiring regeneration

### Phase 4: Quality Documentation

**Purpose:** Document validation and produce evidence for stakeholders

**QA Report Sections:**

**Executive Summary:**
- Overall status (approved/conditional/revisions)
- Quality rating
- Key strengths
- Areas requiring attention

**Technical Validation Results:**
- Automated checks status
- Errors/warnings resolved
- Quality indicators flagged

**Pedagogical Review Results:**
- Questions approved/revised/rejected
- Quality dimension ratings
- Issues by category

**Collective Analysis Results:**
- Coverage validation
- Distribution validation
- Consistency checks
- Assessment character evaluation

**Detailed Findings:**
- Specific issues per question
- Recommended actions
- Priority levels

**Approval Determination:**
- APPROVED FOR DEPLOYMENT: All standards met
- CONDITIONAL APPROVAL: Minimum standards met, enhancements noted
- REVISIONS REQUIRED: Specific corrections before approval
- MAJOR RECONSTRUCTION: Fundamental problems, return to BB4

**Quality Metadata (attached to each question):**
```yaml
quality_assurance:
  validation_date: [date]
  reviewer: [name]
  status: [approved/conditional/revise]
  quality_ratings:
    alignment: [strong/adequate/weak]
    cognitive_accuracy: [matches/lower/higher]
    difficulty: [appropriate/adjustment]
    clarity: [clear/adequate/needs_improvement]
  approval:
    approved_by: [instructor]
    approval_date: [date]
```

---

## VALIDATION WORKFLOWS

### Standard Workflow (New Questions)
BB4 (Generated Questions) → BB5 Phase 1 (Technical) → BB5 Phase 2 (Pedagogical) → BB5 Phase 3 (Collective) → BB5 Phase 4 (Documentation) → BB6 (Export)

**Error Handling:**
- Phase 1 fails → Return to BB4 for technical correction
- Phase 2 identifies issues → Revise in BB4 or minor corrections in BB5
- Phase 3 finds gaps → Return to BB4 for additional generation

### Revision Workflow (Existing Questions)
Existing questions → BB5 diagnostic analysis → Targeted improvements → Re-validation → Approval

### Import Preparation (Technical Only)
Ready questions → BB5 Phase 1 (Technical validation) → BB5 Phase 4 (Documentation) → BB6 (Export)

---

## INTEGRATION POINTS

### From Building Block 4
- Generated questions in structured format
- Initial quality checks passed
- Metadata complete

### To Building Block 6
- Validated question set
- QA approval certificate
- Quality metadata embedded
- Coverage/distribution matrices
- Platform-ready status confirmed

### Quality Preservation Requirements
Building Block 6 must preserve during export:
- All validated content (no modifications)
- All approved metadata
- Question structure as validated
- Pedagogical intent documented in QA

---

## EFFICIENCY GUIDELINES

### For AI Systems
- Conduct automated checks first (eliminate technical distractions)
- Flag potential issues with clear severity levels
- Batch similar issues for efficient review
- Automate straightforward corrections with approval
- Generate concise actionable reports

### For Instructors
- Review questions by learning objective (maintains context)
- Focus on critical issues (alignment, accuracy, clarity)
- Accept "adequate" rather than pursuing "perfect"
- Document significant decisions for future reference
- Use structured protocols (prevents missing dimensions)

### Time Investment
- Technical validation: Automated (~5 minutes)
- Pedagogical review: ~1-2 minutes per question
- Collective analysis: ~15-20 minutes
- Documentation: ~10-15 minutes
- **Total:** 1-2 hours for 40-50 questions

---

## COMMON QUALITY ISSUES

### Technical Issues
- Malformed metadata
- Invalid identifiers
- QTI incompatible structures
- Missing required fields
- Cross-reference errors

### Pedagogical Issues
- Misalignment with objectives
- Cognitive level mismatch
- Inappropriate difficulty
- Unclear language
- Weak distractors
- Inadequate feedback
- Accessibility barriers

### Collective Issues
- Coverage gaps
- Distribution imbalances
- Question dependencies
- Excessive redundancy
- Inconsistent terminology

---

## QUALITY STANDARDS

### Critical (Must Meet)
- ✅ Technical validation passes
- ✅ All questions aligned with objectives
- ✅ Disciplinary accuracy confirmed
- ✅ Minimum coverage requirements met
- ✅ No accessibility barriers

### Important (Should Meet)
- ✅ Cognitive levels accurate
- ✅ Difficulty appropriately calibrated
- ✅ Language clear and appropriate
- ✅ Distribution within tolerance
- ✅ Feedback instructionally valuable

### Desirable (Nice to Have)
- ✅ Excellent distractor quality
- ✅ Authentic scenarios
- ✅ Sophisticated rubrics
- ✅ Extensive coverage variety

---

## BB5 COMPLETION VERIFICATION

**Ready for Building Block 6 when:**
- All automated technical validation passed
- All questions approved or conditionally approved
- Coverage requirements satisfied
- Distribution validated
- QA report completed
- Instructor approval obtained

**Status:** Ready to proceed to Building Block 6 (Export)

---

**Document Status:** BB5 Complete  
**Component:** Building Block 5  
**Previous:** bb4 (Question Generation - to be completed)  
**Next:** bb6 (Export & Integration)  
**Lines:** 351
