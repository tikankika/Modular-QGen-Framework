# OUTPUT FILE STRUCTURE

**Version:** 2.0
**Last Updated:** November 2025
**Purpose:** File organization and format for QTI Generator input
**Part of:** 4-document set (BB6A: Output | BB6B: Metadata | BB6C: Validation | BB6D: File Structure)

---

## TWO-FILE OUTPUT SYSTEM

**Requirement:** Output questions and metadata as TWO separate files

**Rationale:**
- Separation of concerns (content vs metadata)
- Easier bulk editing of metadata
- QTI Generator can process independently
- Reduces duplication in collaborative workflows

---

## FILE 1: QUESTIONS FILE

**Filename:** `questions.md` or `[project_name]_questions.md`

**Contents:** Question content ONLY, no metadata headers

**Structure per question:**
```
## Question 1

### Question Text
[Question content here]

### Options
A. [Option text]
B. [Option text]
C. [Option text]
D. [Option text]

### Answer
B

### Feedback
#### General Feedback
[Unified feedback content]

#### Correct Response Feedback
[Same as General Feedback]

#### Incorrect Response Feedback
[Same as General Feedback]

#### Unanswered Feedback
[Same as General Feedback]

---
```

**Rules:**
- Questions numbered sequentially (Question 1, Question 2, etc.)
- NO Type, Identifier, Points, Language, Tags headers
- Separator (---) between questions
- Follow BB6A structure for question-specific sections
- Use unified feedback (see BB6A INSPERA FEEDBACK REQUIREMENT)

---

## FILE 2: METADATA FILE

**Filename:** `metadata.csv` or `metadata.md`

**Purpose:** Store Type, Identifier, Points, Language, Tags for all questions

### Option A: CSV Format (RECOMMENDED)

**Filename:** `metadata.csv`

**Structure:**
```
Question_Number,Type,Identifier,Points,Language,Tags
1,multiple_choice_single,MC_Q001,1,en,"evolution, darwin, natural selection"
2,true_false,TF_Q002,1,en,"evolution, population"
3,fill_in_the_blank,FITB_Q003,1,en,"allele, genetics"
```

**Rules:**
- Header row required
- Question_Number links to questions.md (1 = Question 1)
- Type must match BB6A valid types
- Identifier must be unique (UPPERCASE_UNDERSCORES)
- Points must be positive integer
- Language must be en|sv|no|da
- Tags comma-separated, quoted if contains commas

### Option B: Markdown Format (ALTERNATIVE)

**Filename:** `metadata.md`

**Structure:**
```
# Question Metadata

## Question 1
**Type:** multiple_choice_single
**Identifier:** MC_Q001
**Points:** 1
**Language:** en
**Tags:** evolution, darwin, natural selection

## Question 2
**Type:** true_false
**Identifier:** TF_Q002
**Points:** 1
**Language:** en
**Tags:** evolution, population
```

**Rules:**
- Question numbers match questions.md
- All 5 required fields present (see BB6B)
- Format exactly as shown

---

## FOLDER STRUCTURE

**Required structure for QTI Generator:**

```
project_name/
├── questions.md          ← Question content
├── metadata.csv          ← Metadata for all questions
└── images/               ← Optional: Images referenced in questions
    ├── diagram1.png
    └── diagram2.png
```

**Alternative structure (markdown metadata):**
```
project_name/
├── questions.md
├── metadata.md
└── images/
```

**Rules:**
- All files in same directory
- Image paths in questions.md: `![alt](images/filename.png)`
- Images folder optional if no images used

---

## LINKING QUESTIONS TO METADATA

**Method:** Question number in questions.md corresponds to row/section in metadata file

**Example:**

**questions.md:**
```
## Question 1
### Question Text
What is evolution?
```

**metadata.csv:**
```
Question_Number,Type,Identifier,Points,Language,Tags
1,multiple_choice_single,MC_Q001,1,en,"evolution, definition"
```

**metadata.md:**
```
## Question 1
**Type:** multiple_choice_single
**Identifier:** MC_Q001
```

**Rule:** Question numbers MUST be sequential (1, 2, 3...) with no gaps

---

## QTI GENERATOR EXPECTATIONS

**Input requirements:**
1. questions.md file with question content
2. metadata file (CSV or MD) with 5 required fields per question
3. Matching question numbers between files
4. All files in same directory

**Processing:**
1. QTI Generator reads questions.md for content
2. Reads metadata file for Type, Identifier, Points, Language, Tags
3. Merges data using Question_Number as key
4. Generates QTI XML files

**Validation:**
- Question count must match between files
- All Question_Numbers must have corresponding metadata
- All required metadata fields must be present (see BB6B)
- Question structure must follow BB6A specifications

---

## MIGRATION FROM SINGLE-FILE FORMAT

**Old format (single file):**
```
**Type:** multiple_choice_single
**Identifier:** MC_Q001
**Points:** 1
**Language:** en
**Tags:** evolution

## Question Text
What is evolution?

## Options
A. Change over time
...

---
```

**New format (two files):**

**questions.md:**
```
## Question 1

### Question Text
What is evolution?

### Options
A. Change over time
...

---
```

**metadata.csv:**
```
Question_Number,Type,Identifier,Points,Language,Tags
1,multiple_choice_single,MC_Q001,1,en,"evolution"
```

**Conversion steps:**
1. Extract Type, Identifier, Points, Language, Tags from each question
2. Create metadata.csv with extracted data
3. Remove metadata headers from questions.md
4. Renumber questions sequentially (## Question 1, ## Question 2, etc.)
5. Verify question counts match

---

## EXAMPLE: COMPLETE PROJECT

**Folder:**
```
test_03_TRA265_L1b/
├── questions.md
├── metadata.csv
└── images/
    ├── biofuel_diagram.png
    └── fossil_pathway.png
```

**questions.md (excerpt):**
```
## Question 1

### Question Text
Compare the WTT stages for fossil fuels vs biofuels using the diagram below:

![Fossil fuel pathway](images/fossil_pathway.png)

### Options
A. Both start with extraction
B. Biofuels start with cultivation, fossil fuels start with extraction
C. Both start with cultivation
D. There is no difference

### Answer
B

### Feedback
#### General Feedback
The fundamental difference is that biofuels are GROWN (cultivation) while fossil fuels are EXTRACTED (drilling/mining). This is the first WTT stage for each pathway. Fossil fuels: extraction → refining → distribution. Biofuels: cultivation → processing → distribution.

#### Correct Response Feedback
The fundamental difference is that biofuels are GROWN (cultivation) while fossil fuels are EXTRACTED (drilling/mining). This is the first WTT stage for each pathway. Fossil fuels: extraction → refining → distribution. Biofuels: cultivation → processing → distribution.

#### Incorrect Response Feedback
The fundamental difference is that biofuels are GROWN (cultivation) while fossil fuels are EXTRACTED (drilling/mining). This is the first WTT stage for each pathway. Fossil fuels: extraction → refining → distribution. Biofuels: cultivation → processing → distribution.

#### Unanswered Feedback
The fundamental difference is that biofuels are GROWN (cultivation) while fossil fuels are EXTRACTED (drilling/mining). This is the first WTT stage for each pathway. Fossil fuels: extraction → refining → distribution. Biofuels: cultivation → processing → distribution.

---

## Question 2

### Question Text
What percentage of total WTW emissions for conventional gasoline vehicles comes from WTT activities?

### Options
A. 5-10%
B. 15-20%
C. 30-40%
D. 45-50%

### Answer
B

### Feedback
#### General Feedback
For conventional gasoline/diesel vehicles, approximately 15-20% of total Well-to-Wheels emissions come from Well-to-Tank activities (extraction, refining, distribution). The remaining 80-85% comes from Tank-to-Wheels (combustion during driving). This can range from 8-27% depending on fuel type and refining efficiency, but 15-20% is typical.

#### Correct Response Feedback
For conventional gasoline/diesel vehicles, approximately 15-20% of total Well-to-Wheels emissions come from Well-to-Tank activities (extraction, refining, distribution). The remaining 80-85% comes from Tank-to-Wheels (combustion during driving). This can range from 8-27% depending on fuel type and refining efficiency, but 15-20% is typical.

#### Incorrect Response Feedback
For conventional gasoline/diesel vehicles, approximately 15-20% of total Well-to-Wheels emissions come from Well-to-Wheels activities (extraction, refining, distribution). The remaining 80-85% comes from Tank-to-Wheels (combustion during driving). This can range from 8-27% depending on fuel type and refining efficiency, but 15-20% is typical.

#### Unanswered Feedback
For conventional gasoline/diesel vehicles, approximately 15-20% of total Well-to-Wheels emissions come from Well-to-Tank activities (extraction, refining, distribution). The remaining 80-85% comes from Tank-to-Wheels (combustion during driving). This can range from 8-27% depending on fuel type and refining efficiency, but 15-20% is typical.

---
```

**metadata.csv:**
```
Question_Number,Type,Identifier,Points,Language,Tags
1,multiple_choice_single,TRA265_L1B_Q001,1,en,"WTT, biofuels, fossil fuels, pathway comparison"
2,multiple_choice_single,TRA265_L1B_Q002,1,en,"WTT, WTW, emissions, fossil fuels"
```

---

## VALIDATION CHECKLIST

**Before QTI generation:**

1. File structure:
   - [ ] questions.md exists
   - [ ] metadata file exists (CSV or MD)
   - [ ] All files in same directory
   - [ ] Images folder exists if images used

2. Question numbering:
   - [ ] Questions numbered sequentially (1, 2, 3...)
   - [ ] No gaps in numbering
   - [ ] Same count in questions.md and metadata file

3. Metadata completeness:
   - [ ] All 5 required fields present (Type, Identifier, Points, Language, Tags)
   - [ ] All Identifiers unique
   - [ ] All Types valid (see BB6A)
   - [ ] All Points positive integers
   - [ ] All Languages valid (en|sv|no|da)

4. Question content:
   - [ ] All questions follow BB6A structure
   - [ ] Unified feedback used (see BB6A)
   - [ ] Image paths correct (if images used)
   - [ ] Separator (---) between questions

---

## TROUBLESHOOTING

**Error: Question count mismatch**
- Check questions.md has same number of questions as metadata rows
- Verify sequential numbering (no skipped numbers)

**Error: Missing metadata field**
- Ensure all 5 required fields in metadata file
- Check CSV header row matches field names

**Error: Invalid Type**
- Verify Type matches BB6A valid types exactly (lowercase_underscores)

**Error: Duplicate Identifier**
- All Identifiers must be unique across all questions
- Use UPPERCASE_UNDERSCORES format

**Error: Image not found**
- Check image path matches folder structure
- Use relative paths: `images/filename.png`

---

## CROSS-REFERENCES

**For question content structure:** See BB6A - Question Output Specifications
**For metadata field specs:** See BB6B - Metadata Requirements
**For validation rules:** See BB6C - Validation Checklist

---

**Document Version:** 2.0
**Classification:** Machine-readable technical specification for Claude Desktop
**Purpose:** Define two-file output format for QTI Generator input
