# METADATA REQUIREMENTS

**Version:** 2.0
**Last Updated:** November 2025
**Purpose:** Metadata field specifications - machine-readable reference for Claude Desktop
**Part of:** 3-document set (BB6A: Output | BB6B: Metadata | BB6C: Validation)

---

## REQUIRED FIELDS

```
Type: lowercase_underscores
Identifier: UPPERCASE_UNDERSCORES
Points: positive integer
Language: en|sv|no|da
Tags: comma-separated keywords
```

**Rules:**
- Type must match one of 16 valid question types
- Identifier must be unique within test
- Points must be positive integer (no text suffix)
- Language must be specified (no default)
- Tags must be present (minimum 1 keyword)

---

## FORMAT SPECIFICATIONS

### Type Field
```
Format: lowercase_underscores
Valid Values:
  multiple_choice_single
  multiple_response
  true_false
  fill_in_the_blank
  text_entry
  inline_choice
  match
  hotspot
  gapmatch
  gap_match
  graphicgapmatch_v2
  text_entry_graphic
  text_area
  extended_text
  audio_record
  composite_editor
  nativehtml

Invalid: CamelCase, Title Case, spaces, hyphens
```

### Identifier Field
```
Format: UPPERCASE_UNDERSCORES
Pattern: [A-Z]+(_[A-Z0-9]+)*
Examples: MC_Q001, TF_Q015, FITB_Q003
Invalid: mc-q-001, mcQ001, MC-Q-001
```

### Points Field
```
Format: positive integer
Examples: 1, 2, 5, 10
Invalid: 2 points, 1.5, 0, -1
Special: nativehtml must have Points: 0
```

### Language Field
```
Format: ISO 639-1 two-letter code
Valid Values:
  en (English)
  sv (Swedish)
  no (Norwegian)
  da (Danish)

QTI Normalization:
  en → en_us
  sv → sv_se
  no → no_no
  da → da_dk

Required: Must be specified for every question
```

### Tags Field
```
Format: comma-separated keywords
Example: evolution, natural selection, genetics
Usage: Exported as searchable labels in IMS manifest
Required: Minimum 1 keyword
```

---

## ANSWER FIELD FORMAT

### Single Choice (multiple_choice_single, true_false)
```
Format: Single letter, plain text
Examples: A, B, C
Invalid: **B**, "C", b
```

### Multiple Choice (multiple_response)
```
Format: Comma-space separated letters
Example: A, C, E
Invalid: A,C,E (no space), A C E (no comma), a, c, e
```

### Match Type
```
Format: Arrow notation, one per line
Example:
1 → A
2 → B
3 → C

Invalid: 1-A, 1:A, 1=A
```

### Fill-in-Blank / Text Entry
```
Format: Plain text string
Notes: Specified in "Correct Answer" section, not "Answer" field
```

---

## CROSS-REFERENCES

**For question output structure:** See BB6A - Question Output Specifications
**For output file structure:** See BB6D - Output File Structure
**For validation rules:** See BB6C - Validation Checklist

---

**Document Version:** 2.0 (split from BB6_v02)
**Classification:** Machine-readable technical specification for Claude Desktop
