# Universal QTI Generator Input Specification

**Purpose**: This is THE MASTER TEMPLATE showing the EXACT markdown format required for the Python QTI Generator to create valid QTI 2.2 XML files for Inspera import.

**Universality**: This specification works for:
- ✅ **All subjects**: Mathematics, Science, History, Languages, Arts, Engineering, Medicine, etc.
- ✅ **All educational levels**: Gymnasium (Gy11/GY25), Högskola, Universitet (Bachelor, Master, PhD)
- ✅ **All assessment types**: Formative, Summative, Diagnostic, Practice

**What determines complexity**: NOT the format (which stays identical), but YOUR content:
- Question difficulty and depth
- Bloom's Taxonomy level (Remember → Create)
- Learning objectives aligned to your curriculum
- Points assigned per question

---

## 📐 THE FORMAT IS UNIVERSAL - THE CONTENT IS YOURS

**Same Format Example:**

**Gymnasium (Simple):**
```markdown
# Question 1: Basic Photosynthesis

**Type**: multiple_choice_single
**Identifier**: GYM_Q001
**Points**: 1
**Bloom's Level**: Remember

## Question Text
What happens during photosynthesis?
```

**University (Advanced):**
```markdown
# Question 1: Photosystem II Electron Transport

**Type**: multiple_choice_single
**Identifier**: UNI_Q001
**Points**: 3
**Bloom's Level**: Analyze

## Question Text
During quantitative analysis of Photosystem II in *Arabidopsis*, P680+ reduction rate decreases at pH 6.2 vs pH 7.4. What is the most likely molecular explanation?
```

**→ SAME FORMAT, DIFFERENT CONTENT COMPLEXITY!**

---

## ✅ EXACT FORMAT SPECIFICATION

### 1. File Header - YAML Frontmatter (REQUIRED)

**Location**: Top of file
**Delimiters**: Three dashes `---` on separate lines

```yaml
---
test_metadata:
  title: "[Your Assessment Title]"
  identifier: "[UNIQUE_TEST_ID]"  # Examples: MATH101_EXAM, BIOG_QUIZ_2025
  language: "[ISO-CODE]"  # sv, en, no, da, fi, etc.
  description: "[Brief description of assessment purpose and coverage]"
  subject: "[Course Code or Subject Area]"
  author: "[Your Name]"
  created_date: "[YYYY-MM-DD]"

assessment_configuration:
  type: "[formative or summative]"
  time_limit: [minutes]  # Optional, use null if no limit
  shuffle_questions: [true or false]
  shuffle_choices: [true or false]
  feedback_mode: "[immediate, deferred, or none]"
  attempts_allowed: [number or unlimited]

learning_objectives:
  - id: "LO1"
    description: "[Students will be able to... / Eleven ska kunna...]"
  - id: "LO2"
    description: "[Students will be able to... / Studenten ska kunna...]"
  - id: "LO3"
    description: "[Your learning objective description]"
  # Add as many as needed (typically 5-15 for a complete assessment)
---
```

**Examples for Different Subjects:**

**Mathematics:**
```yaml
learning_objectives:
  - id: "LO1"
    description: "Calculate derivatives of polynomial functions"
  - id: "LO2"
    description: "Apply chain rule to composite functions"
```

**History:**
```yaml
learning_objectives:
  - id: "LO1"
    description: "Analyze causes of the French Revolution"
  - id: "LO2"
    description: "Evaluate impact of Enlightenment on modern democracy"
```

**Language (Swedish):**
```yaml
learning_objectives:
  - id: "LO1"
    description: "Konjugera oregelbundna verb i presens och preteritum"
  - id: "LO2"
    description: "Analysera grammatiska strukturer i autentiska texter"
```

---

## 📋 REQUIRED vs OPTIONAL FIELDS

### Required Fields (Parser will fail without these):

**Per Question:**
- `**Type**:` - Question type (must be exact spelling)
- `**Identifier**:` - Unique ID for the question
- `**Points**:` - Point value

**Per File (YAML frontmatter):**
- `title` - Assessment title
- `identifier` - Unique test ID
- `language` - ISO language code

### Optional Fields (Enhance functionality, become Inspera labels):

**Per Question:**
- `**Learning Objectives**:` - Which LOs this question assesses (becomes searchable label in Inspera)
- `**Bloom's Level**:` - Cognitive complexity level (becomes searchable label in Inspera)

**Why include optional fields?**
✅ They automatically become **searchable labels/tags** in Inspera question bank
✅ Enable filtering by learning objective or Bloom's level
✅ Support curriculum alignment reporting
✅ Help organize large question banks
✅ No downside - if included, they're useful; if omitted, question still works

**Example in Inspera:**
When you include `**Learning Objectives**: LO1, LO2` and `**Bloom's Level**: Analyze`, Inspera creates searchable tags:
- Label: "LO1"
- Label: "LO2"
- Label: "Analyze"
- Label: "[Subject from YAML]"
- Label: "multiple_choice_single"

This makes it easy to find all "Analyze" level questions about "LO1" later!

---

### 2. Question Structure - Multiple Choice Single

**Question Heading**: Single `#` (H1 level)
**Format**: `# Question [N]: [Descriptive Title]`

```markdown
# Question 1: [Brief Descriptive Title]

## REQUIRED FIELDS:
**Type**: multiple_choice_single
**Identifier**: [Q001, MC_001, YOUR_ID_FORMAT]
**Points**: [1-5 typically]

## OPTIONAL FIELDS (become Inspera searchable labels if included):
**Learning Objectives**: [LO1, LO2]  # Can reference multiple
**Bloom's Level**: [Remember|Understand|Apply|Analyze|Evaluate|Create]

## Question Text

[Your question prompt here. Can include:]
- Regular text with **bold** and *italic*
- Mathematical notation: $f(x) = x^2 + 3x - 5$
- Images: ![description](path/to/image.png)
- Code blocks for programming questions
- Tables, lists, and other markdown formatting

## Options

A. [First option text]
B. [Second option text]
C. [Third option text]
D. [Fourth option text]
[E. Fifth option if needed]

## Answer

[Single letter - e.g., B]

## Feedback

### General Feedback
[Context or background information shown to all students regardless of answer]

### Correct Response Feedback
[Positive reinforcement and explanation of why the answer is correct]

### Incorrect Response Feedback
[Guidance toward correct understanding without revealing the answer]

### Option-Specific Feedback
- **A**: [Explanation of why this option is incorrect / what misconception it represents]
- **B**: [Confirmation that this is correct and additional explanation]
- **C**: [Explanation of why this option is incorrect]
- **D**: [Explanation of why this option is incorrect]

### Unanswered Feedback
[Reminder to answer the question]

---
```

**Question Separator**: Always use `---` on its own line between questions

---

### 3. Question Structure - Multiple Response (Select All)

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: multiple_response
**Identifier**: [YOUR_ID]
**Points**: [Total points]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1, LO2]
**Bloom's Level**: [Level]

## Question Text

[Question prompt - do NOT include "Select all that apply" here]

## Prompt

[Select all that apply. / Välj alla korrekta påståenden. / Choose all correct options.]

## Options

A. [Option text]
B. [Option text]
C. [Option text]
D. [Option text]
E. [Option text]

## Answer

[Comma-separated letters - e.g., A, C, E]

## Scoring

**Points per correct choice**: [e.g., 0.67 or 1]
**Points per incorrect choice**: [e.g., 0 or -0.5]
**Maximum score**: [Total points]
**Minimum score**: [Usually 0]

## Feedback

### General Feedback
[General information]

### Correct Response Feedback
[All correct - excellent work]

### Incorrect Response Feedback
[None or some wrong - guidance]

### Partially Correct Response Feedback
[Some correct - encouragement and direction]

### Option-Specific Feedback
- **A**: [Why this is correct/incorrect]
- **B**: [Why this is correct/incorrect]
- **C**: [Why this is correct/incorrect]
- **D**: [Why this is correct/incorrect]
- **E**: [Why this is correct/incorrect]

### Unanswered Feedback
[Prompt to answer]

---
```

---

### 4. Question Structure - True/False

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: true_false
**Identifier**: [YOUR_ID]
**Points**: [Usually 1]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1]
**Bloom's Level**: [Level]

## Question Text

[True or false: Statement to evaluate]
[Sant eller falskt: Påstående att bedöma]

## Options

A. [True / Sant]
B. [False / Falskt]

## Answer

[A or B]

## Feedback

### General Feedback
[Context about the concept]

### Correct Response Feedback
[Confirmation and explanation]

### Incorrect Response Feedback
[Correction and guidance]

### Unanswered Feedback
[Reminder to answer]

---
```

---

### 5. Question Structure - Fill-in-the-Blank

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: fill_in_the_blank
**Identifier**: [YOUR_ID]
**Points**: [Usually 1-2]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1]
**Bloom's Level**: [Remember or Understand typically]

## Question Text

[Text with blank marked as **________** or __________]
Example: The derivative of $x^2$ is **________**.

## Correct Answer

[primary answer]

## Accepted Alternatives

[answer1, answer2, answer3]  # Comma-separated, no bullets

## Case Sensitive

[true or false]

## Expected Length

[Number - approximate character length for UI field sizing]

## Feedback

### General Feedback
[Context about the concept]

### Correct Response Feedback
[Confirmation and explanation]

### Incorrect Response Feedback
[Guidance without revealing answer]

### Unanswered Feedback
[Prompt to fill in the blank]

---
```

---

### 6. Question Structure - Matching (Associate Pairs)

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: match
**Identifier**: [YOUR_ID]
**Points**: [Total points]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1, LO2]
**Bloom's Level**: [Understand or Apply typically]

## Question Text

[Instructions for matching task]
Example: Match each [concept] with its [definition/example/application].

## Premises (Left Column)

1. [First item to match]
2. [Second item to match]
3. [Third item to match]

## Choices (Right Column)

A. [First choice]
B. [Second choice]
C. [Third choice]
D. [Optional fourth choice - distractor]

## Answer

1 → [A, B, or C]
2 → [A, B, or C]
3 → [A, B, or C]

## Scoring

**Type**: partial_credit
**Points per correct match**: [e.g., 1]
**Minimum score**: [Usually 0]

## Feedback

### General Feedback
[Context about the concepts being matched]

### Correct Response Feedback
[All correct - excellent]

### Incorrect Response Feedback
[Guidance for wrong matches]

### Partially Correct Response Feedback
[Some correct - encouragement]

### Unanswered Feedback
[Prompt to complete matching]

---
```

---

### 7. Question Structure - Text Area (Short Response)

**Note**: This type requires manual grading

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: text_area
**Identifier**: [YOUR_ID]
**Points**: [Usually 2-5]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1, LO2]
**Bloom's Level**: [Apply, Analyze, or Evaluate typically]

## Question Text

[Open-ended question requiring written response]
[Specify expected length: 50-100 words, 3-5 sentences, etc.]

## Rubric

[Scoring criteria - what constitutes full, partial, and no credit]

## Sample Answer

[Example of a complete, correct response]

## Feedback

### General Feedback
[Context about the question]

### Unanswered Feedback
[Prompt to provide answer]

---
```

---

### 8. Question Structure - Extended Text (Essay)

**Note**: This type requires manual grading

```markdown
# Question [N]: [Title]

## REQUIRED:
**Type**: extended_text
**Identifier**: [YOUR_ID]
**Points**: [Usually 5-15]

## OPTIONAL (Inspera labels):
**Learning Objectives**: [LO1, LO2, LO3]
**Bloom's Level**: [Analyze, Evaluate, or Create]

## Question Text

[Essay prompt with clear expectations]
[Specify length: 300-500 words, 2-3 paragraphs, etc.]

## Rubric

[Detailed scoring criteria]
[Consider: argument quality, evidence use, organization, writing quality]

## Sample Answer

[Example of high-quality response]

## Feedback

### General Feedback
[Context and expectations]

### Unanswered Feedback
[Prompt to write essay]

---
```

---

## ⚠️ CRITICAL FORMAT RULES (UNIVERSAL - NEVER CHANGE)

### Question Header Fields

**REQUIRED Fields (Parser fails without these):**

1. **Type** - EXACT spelling required (lowercase, underscores):
   - `multiple_choice_single`
   - `multiple_response`
   - `true_false`
   - `fill_in_the_blank`
   - `match`
   - `text_area`
   - `extended_text`
   - `audio_record`
   - `nativehtml`

2. **Identifier** - Unique question ID:
   - UPPERCASE letters, numbers, underscores only
   - No spaces, no special characters
   - Examples: `Q001`, `MC_001`, `MATH_Q15`, `HIST_ESSAY_1`

3. **Points** - Point value (number)

**OPTIONAL Fields (Become Inspera searchable labels if included):**
- **Learning Objectives**: References to LO IDs from YAML (e.g., `LO1, LO2`)
- **Bloom's Level**: Cognitive level (Remember, Understand, Apply, Analyze, Evaluate, Create)

**Section Headers** (must be EXACT, H2 level with `##`):
- `## Question Text` (NOT "### Question" or "## Frågetext")
- `## Options` (NOT "## Choices" or "## Alternativ")
- `## Answer` (NOT "## Correct Answer" or "## Svar")
- `## Feedback` (NOT "## Återkoppling")
- `## Prompt` (for multiple_response only)
- `## Premises (Left Column)` (for match)
- `## Choices (Right Column)` (for match)
- `## Correct Answer` (for fill_in_the_blank)
- `## Accepted Alternatives` (for fill_in_the_blank)
- `## Case Sensitive` (for fill_in_the_blank)
- `## Expected Length` (for fill_in_the_blank)
- `## Scoring` (for multiple_response and match)

**Feedback Subsections** (must be EXACT, H3 level with `###`):
- `### General Feedback`
- `### Correct Response Feedback`
- `### Incorrect Response Feedback`
- `### Partially Correct Response Feedback` (for MR and Match)
- `### Option-Specific Feedback` (for MC and MR)
- `### Unanswered Feedback`

**Answer Format**:
- Multiple Choice Single: Single letter `B` (no bold, no period, no quotes)
- Multiple Response: Comma-separated `A, C, E`
- True/False: `A` (where A=True/Sant, B=False/Falskt)
- Match: One pairing per line `1 → A` or `1 -> A`
- Fill-in-the-blank: Plain text under `## Correct Answer`

**Question Separator**:
- Three dashes `---` on its own line
- One blank line before and after recommended

---

## 🎯 ADAPTING FOR YOUR COURSE

### Step 1: Customize YAML Frontmatter

**Choose appropriate:**
- `title`: Your assessment name
- `identifier`: Unique ID with your course code
- `language`: Your language code (sv, en, no, etc.)
- `subject`: Your course code or subject area
- `type`: formative (practice, low stakes) vs summative (graded, high stakes)

**Write Learning Objectives aligned to:**
- **Gymnasium**: Gy11/GY25 centralt innehåll and kunskapskrav
- **Högskola/Universitet**: Course syllabus learning outcomes
- **International**: Your curriculum standards

### Step 2: Write Questions at Appropriate Level

**Gymnasium Questions** typically:
- Use Bloom's levels: Remember, Understand, Apply
- Award 1-2 points per question
- Use clear, direct language
- Test foundational knowledge
- Refer to textbook sections

**University Questions** typically:
- Use Bloom's levels: Apply, Analyze, Evaluate, Create
- Award 2-5 points per question
- Use discipline-specific terminology
- Test critical thinking and synthesis
- Reference research articles or case studies

### Step 3: Choose Appropriate Question Types

| Learning Goal | Best Question Type | Example |
|---------------|-------------------|---------|
| Recall facts/definitions | Fill-in-the-blank, MC Single | "The capital of Sweden is ________" |
| Understand concepts | MC Single, True/False | "Explain why photosynthesis requires..." |
| Apply procedures | MC Single, Multiple Response | "Calculate the derivative of..." |
| Analyze relationships | Match, Multiple Response | "Match each cause with its effect" |
| Evaluate arguments | MC Single, Text Area | "Which interpretation is best supported..." |
| Create solutions | Extended Text, Text Area | "Design an experiment to test..." |

---

## 📊 EXAMPLE: SAME QUESTION ACROSS LEVELS

### Gymnasium Level (Basic)

```markdown
# Question 1: Pythagorean Theorem Application

## REQUIRED:
**Type**: multiple_choice_single
**Identifier**: GYM_MATH_Q001
**Points**: 1

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO1
**Bloom's Level**: Apply

## Question Text

En rätrutig triangel har kateterna 3 cm och 4 cm. Hur lång är hypotenusan?

## Options

A. 5 cm
B. 7 cm
C. 12 cm
D. 25 cm

## Answer

A

## Feedback

### General Feedback
Pythagoras sats säger att $a^2 + b^2 = c^2$ där $c$ är hypotenusan.

### Correct Response Feedback
Rätt! $3^2 + 4^2 = 9 + 16 = 25 = 5^2$, så hypotenusan är 5 cm.

### Incorrect Response Feedback
Kom ihåg att använda Pythagoras sats: $a^2 + b^2 = c^2$. Kvadrera kateterna, lägg ihop, och ta kvadratroten.

### Option-Specific Feedback
- **A**: Korrekt! Detta är det rätta svaret enligt Pythagoras sats.
- **B**: Fel. Du kan inte bara addera kateterna: $3 + 4 = 7$ är inte korrekt.
- **C**: Fel. Detta är produkten av kateterna, inte hypotenusan.
- **D**: Fel. Detta är $a^2 + b^2$ utan att ta kvadratroten.

### Unanswered Feedback
Använd Pythagoras sats för att beräkna hypotenusan.

---
```

### University Level (Advanced)

```markdown
# Question 1: Generalized Pythagorean Theorem in Banach Spaces

## REQUIRED:
**Type**: multiple_choice_single
**Identifier**: UNI_MATH_Q001
**Points**: 3

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO1, LO2
**Bloom's Level**: Analyze

## Question Text

Let $X$ be a Banach space with norm $\|\cdot\|$ satisfying the parallelogram law. For orthogonal vectors $x, y \in X$, which generalization of the Pythagorean theorem holds?

## Options

A. $\|x + y\|^2 = \|x\|^2 + \|y\|^2$
B. $\|x + y\| = \|x\| + \|y\|$
C. $\|x + y\|^p = \|x\|^p + \|y\|^p$ for all $p \geq 1$
D. $\langle x+y, x+y \rangle = \langle x,x \rangle + \langle y,y \rangle$

## Answer

A

## Feedback

### General Feedback
The parallelogram law characterizes inner product spaces among Banach spaces, enabling geometric concepts like orthogonality.

### Correct Response Feedback
Correct! In spaces satisfying the parallelogram law, orthogonal vectors satisfy the Pythagorean identity $\|x + y\|^2 = \|x\|^2 + \|y\|^2$, which follows from $\langle x, y \rangle = 0$.

### Incorrect Response Feedback
Consider how the inner product relates to the norm: $\|x + y\|^2 = \langle x+y, x+y \rangle = \|x\|^2 + 2\langle x,y \rangle + \|y\|^2$. What happens when $x \perp y$?

### Option-Specific Feedback
- **A**: Correct. This is the Pythagorean theorem for inner product spaces.
- **B**: Incorrect. This is the triangle equality, which only holds when vectors are parallel and same direction.
- **C**: Incorrect. The Pythagorean identity uses $p=2$, not arbitrary $p$. This would only hold in $\ell^2$ spaces, not general $\ell^p$.
- **D**: Incorrect syntax. While the idea is right, inner products aren't defined in general Banach spaces - only those satisfying the parallelogram law.

### Unanswered Feedback
Consider the relationship between inner products, norms, and orthogonality in Banach spaces.

---
```

**→ SAME FORMAT, DRAMATICALLY DIFFERENT COMPLEXITY!**

---

## 📚 SUBJECT-SPECIFIC EXAMPLES

### Mathematics
```markdown
## REQUIRED:
**Type**: multiple_choice_single
**Identifier**: MATH_Q001
**Points**: 1

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO1
**Bloom's Level**: Apply

## Question Text
Solve for $x$: $2x + 5 = 13$
```

### Science (Biology)
```markdown
## REQUIRED:
**Type**: text_area
**Identifier**: BIO_Q001
**Points**: 3

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO2, LO3
**Bloom's Level**: Analyze

## Question Text
Explain how natural selection acts on variation within a population to drive evolutionary change.
```

### History
```markdown
## REQUIRED:
**Type**: extended_text
**Identifier**: HIST_Q001
**Points**: 5

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO1
**Bloom's Level**: Evaluate

## Question Text
To what extent were economic factors the primary cause of the French Revolution?
```

### Language (Swedish Grammar)
```markdown
## REQUIRED:
**Type**: multiple_choice_single
**Identifier**: SV_Q001
**Points**: 1

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO1
**Bloom's Level**: Apply

## Question Text
Välj rätt verbform: "Igår ________ (gå) jag till affären."

## Options
A. går
B. gick
C. gått
D. gående
```

### Programming
```markdown
## REQUIRED:
**Type**: multiple_choice_single
**Identifier**: PROG_Q001
**Points**: 2

## OPTIONAL (Inspera labels):
**Learning Objectives**: LO2
**Bloom's Level**: Apply

## Question Text
What is the output of this Python code?
\`\`\`python
def f(x):
    return x ** 2
print(f(3))
\`\`\`

## Options
A. 6
B. 9
C. 3
D. Error
```

---

## ✅ UNIVERSAL VALIDATION CHECKLIST

Before running QTI generator, verify:

### Structural
- [ ] YAML frontmatter present and valid (test with yaml parser)
- [ ] All questions use `# Question [N]:` (H1 level, not H2)
- [ ] Questions separated by `---` on its own line
- [ ] No organizational section headers between questions

### Question Headers
- [ ] All questions have REQUIRED fields: Type, Identifier, Points
- [ ] Type field uses EXACT spelling (lowercase_underscore)
- [ ] All Identifiers are unique and valid format (UPPERCASE)
- [ ] OPTIONAL: Learning Objectives (if included) reference IDs defined in YAML
- [ ] OPTIONAL: Bloom's Level (if included) uses correct capitalization

### Section Headers
- [ ] All section headers use `##` (H2 level, not H3)
- [ ] Section headers use EXACT English names
- [ ] No Swedish/Norwegian/Danish headers (`Frågetext`, `Svar`, etc.)

### Content
- [ ] Options format: `A. Text` (uppercase letter, period, space)
- [ ] Answer format matches question type (no bold, no quotes)
- [ ] All required sections present per question type
- [ ] Feedback has proper subsection structure

### Question Type Specific
- [ ] Multiple Response: Has `## Prompt` and `## Scoring`
- [ ] Match: Has `## Premises (Left Column)` and `## Choices (Right Column)` and `## Scoring`
- [ ] Fill-in-the-blank: Has `## Correct Answer`, `## Accepted Alternatives`, `## Case Sensitive`, `## Expected Length`

---

## 🚀 WORKFLOW: FROM TEMPLATE TO INSPERA

### 1. Copy This Template
Save as: `[your_course]_quiz.md`

### 2. Customize YAML Frontmatter
- Fill in your course information
- Write learning objectives for your course
- Configure assessment settings

### 3. Write Questions
- Follow EXACT format for each question type
- Write content at appropriate level for your students
- Create comprehensive feedback

### 4. Validate Format
Use the checklist above

### 5. Generate QTI XML
```bash
python -m src.main [your_course]_quiz.md -o output/
```

### 6. Import to Inspera
- Upload the generated ZIP file
- Review in question bank
- Create test/quiz using questions

---

## 📖 COMPLETE TEMPLATE STRUCTURE

```markdown
---
[YAML FRONTMATTER - Customize for your course]
---

# Question 1: [Your First Question]
[Complete question following type-specific format]

---

# Question 2: [Your Second Question]
[Complete question following type-specific format]

---

# Question 3: [Your Third Question]
[Complete question following type-specific format]

---

[... continue for all questions ...]

---

# Question N: [Your Last Question]
[Complete question following type-specific format]
```

---

## 💡 TIPS FOR SUCCESS

### For Gymnasium
- Use clear, direct language
- Reference textbook sections in General Feedback
- Use concrete, familiar examples
- Focus on Bloom's Remember, Understand, Apply
- Award 1-2 points per question typically

### For University
- Use discipline-specific terminology
- Reference research literature in General Feedback
- Use abstract, theoretical examples
- Focus on Bloom's Apply, Analyze, Evaluate, Create
- Award 2-5 points per question typically
- Include case studies and scenarios

### For All Levels
- ✅ Keep questions focused on one concept
- ✅ Write clear, unambiguous question text
- ✅ Create plausible distractors that reveal misconceptions
- ✅ Provide explanatory feedback, not just "Correct!"/"Wrong!"
- ✅ Align questions to learning objectives
- ✅ Test understanding, not memorization (when possible)

---

## 🔧 TROUBLESHOOTING

### Common Parser Errors

| Error | Cause | Fix |
|-------|-------|-----|
| "No YAML frontmatter" | Missing `---` delimiters | Add `---` before and after YAML |
| "Invalid question type" | Wrong Type spelling | Use exact: `multiple_choice_single` not "Multiple Choice" |
| "Missing required field" | No Identifier or Points | Add to question header |
| "Invalid section header" | Wrong level or name | Use `## Question Text` (H2, English) |
| "Malformed answer" | Extra formatting | Use plain text: `B` not `**B**` |

---

## 📞 SUPPORT

For issues with:
- **This specification**: Check examples and format rules
- **Python QTI generator**: Check project documentation
- **Inspera import**: Consult Inspera support
- **Subject-specific pedagogy**: Consult your curriculum guides

---

**Document Version**: 1.0
**Created**: 2025-11-02
**Purpose**: Universal master template for QTI question generation across all subjects and levels
**Replaces**: Subject-specific templates (but can coexist as examples)
