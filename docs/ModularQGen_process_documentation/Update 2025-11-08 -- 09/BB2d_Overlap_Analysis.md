# BB2d OVERLAP ANALYSIS

**File Analyzed:** MQG_bb2d_Stage3_Question_Target.md  
**Analysis Date:** November 10, 2025  
**Total Lines:** 186  

---

## OVERLAPS IDENTIFIED

### 1. Time Constraint Reference (APPROPRIATE CROSS-REFERENCE)

**Location in bb2d:** Lines 27-29, 56-76 (Time-based constraint validation)
- References "available time" from Stage 2
- Provides detailed question timing estimates
- Validates feasibility against time constraints

**Location in bb2c:** Lines 111-115 (Practical Constraints - Time Available)
- Documents how much time available for assessment
- Explains constraint influence on question count

**Type:** Appropriate cross-reference - bb2c establishes constraint, bb2d applies it

**Severity:** ZERO - Perfect separation of concerns

**Recommendation:** KEEP BOTH
- bb2c: Documents the time constraint
- bb2d: Uses that constraint in calculations
- Proper modular design

---

### 2. Question Type Timing Data (UNIQUE TO BB2d - NO DUPLICATION)

**Location in bb2d:** Lines 35-55 (Detailed timing per question type)
- Selected-response formats: 30-120 seconds
- Constructed-response formats: 3-30 minutes
- Interactive formats: 45-180 seconds
- Specific timing ranges for 10 question types

**Checked against bb2f:** (Question Type Mix Planning)
- bb2f describes question type affordances and uses
- bb2f mentions "completion time" as factor but no specific timings
- bb2f focuses on cognitive mapping, not timing

**Type:** Unique Stage 3 content - essential for feasibility calculation

**Severity:** ZERO - No overlap

**Recommendation:** KEEP
- bb2d needs timing data for feasibility validation
- bb2f doesn't duplicate this - different purposes
- Critical for Stage 3 calculations

---

### 3. Coverage-Based Question Ratios (UNIQUE TO BB2d)

**Location in bb2d:** Lines 17-24 (Coverage minimum calculations)
- 2 questions per objective: Minimal coverage
- 3-4 questions per objective: Adequate coverage
- 4-6 questions per objective: Robust coverage
- 6+ questions per objective: Extensive coverage

**Checked against:** All other bb2 files

**Type:** Unique Stage 3 content

**Severity:** ZERO - No overlap found

**Recommendation:** KEEP - Essential assessment design principle for Stage 3

---

### 4. Tier-Based Distribution Concept (APPROPRIATE REFERENCE)

**Location in bb2d:** Lines 108-123 (Uneven objective distribution)
- References Tier 1/Tier 2 objectives from Building Block 1
- Suggests weighted distribution option
- 60% questions for Tier 1, 40% for Tier 2 as example

**Also referenced in:**
- bb2b: References BB1 tiers for objective validation
- bb2c: Implicit in assessment strategy
- Multiple files: Tier system is framework-wide concept

**Type:** Appropriate use of framework-wide concept

**Severity:** ZERO - Consistent framework terminology

**Recommendation:** KEEP
- Tier concept established in BB1
- Multiple BB2 stages correctly reference it
- Not duplication - proper cross-referencing

---

### 5. Question Type Distribution Mention (FORWARD REFERENCE)

**Location in bb2d:** Lines 140-142 (Stage 3 checkpoint preview)
- "Next stage will determine how these [N] questions distribute across..."
- Lists: Bloom's levels, Question types, Difficulty levels

**Type:** Forward reference to upcoming stages

**Severity:** ZERO - Appropriate navigation aid

**Recommendation:** KEEP - Helps users understand process flow

---

### 6. Practical Constraints (Platform, Grading, Enrollment) (REFERENCE ONLY)

**Location in bb2d:** Lines 27-29 (Brief mention in purpose)
- References "time constraints" and "assessment purpose"
- Does NOT detail all constraints

**Detailed in bb2c:** Lines 111-152
- Time Available (detailed)
- Student Preparation Level (detailed)
- Platform Capabilities (detailed)
- Grading Resources (detailed)
- Student Population Size (detailed)

**Type:** bb2d references, bb2c establishes - proper separation

**Severity:** ZERO - No duplication

**Recommendation:** KEEP BOTH
- bb2c: Establishes and documents constraints
- bb2d: References them for calculations
- Perfect modular design

---

### 7. Stage Checkpoint Format (INTENTIONAL REPETITION)

**Location in bb2d:** Lines 124-186 (Stage 3 Checkpoint + Completion)

**Present in:** All stage files (bb2b-bb2h)

**Type:** Safety mechanism - intentional repetition

**Severity:** ZERO - Deliberate and necessary

**Recommendation:** KEEP ALL
- Stage gates must be explicit in every stage file
- Prevents improvisation and auto-advancement
- Critical framework integrity mechanism

---

## OVERLAPS WITH OTHER STAGES

### 8. Question Count Calculation Flow (APPROPRIATE STAGE PROGRESSION)

**bb2b (Stage 1):** Validates learning objectives exist
**bb2c (Stage 2):** Establishes purpose and constraints
**bb2d (Stage 3):** Calculates question target using objectives + constraints ⬅ CURRENT
**bb2e (Stage 4):** Distributes questions across Bloom's levels
**bb2f (Stage 5):** Determines question type mix
**bb2g (Stage 6):** Determines difficulty distribution

**Type:** Sequential stage progression - each builds on previous

**Severity:** ZERO - This is correct workflow design

**Recommendation:** KEEP - Proper stage dependencies

---

## CONTENT GAPS IN BB2d

### Gap 1: No Prerequisites Note (VERY LOW PRIORITY)

**Issue:** Like bb2b and bb2c before enhancement, bb2d jumps straight into content

**Impact:** Minor - users following sequential flow have context

**Recommendation:** ADD optional prerequisites note (VERY LOW priority):
```markdown
**Prerequisites:** 
- bb2b (Stage 1): Learning objectives validated
- bb2c (Stage 2): Assessment purpose and constraints established

This stage uses objective count and time constraints from previous stages.
```

---

### Gap 2: No Example of Weighted Distribution Calculation (OPTIONAL)

**Location:** Lines 108-123 mention weighted distribution

**Issue:** Provides concept but no worked example showing calculation

**Impact:** Very minor - concept is clear, example would just add clarity

**Recommendation:** OPTIONAL enhancement (LOW priority):
```markdown
Example weighted distribution:
Total: 20 questions, 5 objectives (3 Tier 1, 2 Tier 2)

Weighted approach:
- Tier 1: 60% × 20 = 12 questions ÷ 3 objectives = 4 questions/objective
- Tier 2: 40% × 20 = 8 questions ÷ 2 objectives = 4 questions/objective

vs. Even approach:
- All tiers: 20 questions ÷ 5 objectives = 4 questions/objective

(In this example, even distribution happens to match weighted due to numbers)
```

**Priority:** LOW - Current explanation adequate

---

### Gap 3: What if Coverage-Based Target Conflicts with Time? (ADDRESSED)

**Issue:** Could be unclear what happens when coverage needs exceed time

**Current Status:** ✅ ALREADY ADDRESSED in lines 77-81
- bb2d provides three options: reduce questions, extend time, split sessions

**Impact:** None - already handled well

**Recommendation:** No action needed

---

## SUMMARY OF FINDINGS

### Overlap Severity: ZERO

**Total Overlaps Examined:** 8 instances

**Critical Overlaps:** 0 (none requiring removal)

**Moderate Overlaps:** 0 (none requiring revision)

**Low-Severity Overlaps:** 0 (none found)

**Appropriate Cross-References:** 8 (all serving correct purposes)

---

## RECOMMENDED ACTIONS

### For bb2d (2 optional enhancements - both LOW priority):

1. **Add prerequisites note** (VERY LOW priority):
   ```markdown
   **Prerequisites:** 
   - bb2b (Stage 1): Learning objectives validated
   - bb2c (Stage 2): Assessment purpose and constraints established
   
   This stage uses objective count and time constraints from previous stages.
   ```
   **Location:** After header, before "STAGE 3: QUESTION TARGET DETERMINATION"

2. **Add weighted distribution example** (LOW priority):
   - Worked example showing Tier 1/Tier 2 calculation
   - Comparison with even distribution
   - ~8-10 lines
   **Location:** Within "Uneven Objective Distribution Consideration" section (after line 123)

**Total Changes:** 2 optional additions, 0 removals, ~12-15 lines if both implemented

---

## ASSESSMENT

**Overall bb2d Quality:** EXCELLENT

**Structural Integrity:** ✅ Perfect stage-specific design

**Content Uniqueness:** ✅ All core content unique to Stage 3

**Overlap Issues:** ✅ ZERO problematic overlaps

**Practical Utility:** ✅ Clear calculation frameworks and decision support

**Cross-References:** ✅ Appropriate references to previous stages

---

## DETAILED EVALUATION

### Coverage-Based Calculation Framework ✅

**Excellent pedagogical foundation:**
- Clear rationale: multiple questions per objective for reliability
- Research-informed ranges: 2, 3-4, 4-6, 6+ questions/objective
- Purpose-aligned recommendations: adequate for formative, robust for summative
- Provides starting point while allowing adjustment

**Quality of explanation:** Clear, justified, actionable

---

### Time-Based Feasibility Validation ✅

**Comprehensive timing framework:**
- Specific timing ranges for 10 question types
- Selected-response: 30-120 seconds
- Constructed-response: 3-30 minutes
- Interactive: 45-180 seconds
- Weighted average calculation method provided
- Feasibility assessment logic clear

**Practical value:** Essential for realistic assessment design

**No duplication with bb2f:** bb2f doesn't include timing data

---

### Dialogue Pattern Quality ✅

**Target negotiation dialogue:**
- Presents coverage-based recommendation with rationale
- Validates time feasibility
- Offers clear options when conflicts arise
- Respects teacher decision authority
- Examples of common teacher response patterns

**Strengths:**
- Balances pedagogical ideals with practical constraints
- Transparent about trade-offs
- Multiple resolution pathways

---

### Uneven Distribution Framework ✅

**Tier-based weighting:**
- References BB1 tier system appropriately
- Provides clear example (60/40 split)
- Explains rationale for weighted approach
- Offers even distribution as alternative
- Leaves decision to teacher

**Minor enhancement opportunity:** 
- Worked calculation example would add clarity (LOW priority)

---

### Stage 3 Outputs ✅

**Clear deliverables:**
- Question target number
- Rationale (coverage + time validation)
- Distribution approach (even or weighted)
- Coverage adequacy assessment

**Transition to Stage 4:** 
- Clear preview of what comes next
- Proper stage gate implementation

---

## CONCLUSION

BB2d (Stage 3: Question Target Determination) is excellently designed with ZERO overlap concerns. All content is unique and essential for Stage 3. Cross-references to previous stages (bb2c constraints, BB1 tiers) are appropriate and non-duplicative. The calculation frameworks are clear, pedagogically sound, and practically useful.

**Main Actions (both optional, LOW priority):**
1. Add prerequisites note
2. Add weighted distribution calculation example

**Priority:** LOW - bb2d functions excellently as-is

All "overlaps" examined are actually appropriate cross-references or intentional framework-wide concepts, not duplications requiring removal.

---

**Analysis Complete:** bb2d overlap analysis  
**Status:** ✅ ZERO OVERLAP ISSUES  
**Recommended Revisions:** 2 optional enhancements  
**Priority:** LOW (optional only, no problems found)
