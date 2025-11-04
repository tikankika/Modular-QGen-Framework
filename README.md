# Modular QGen
## Modular Question Generation Framework

**A component-based approach to AI-assisted assessment development**

[![Version](https://img.shields.io/badge/version-0.0.1-blue.svg)](CHANGELOG.md)
[![License](https://img.shields.io/badge/license-CC%20BY%204.0-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-early--stage-yellow.svg)]()

---

## What is Modular QGen?

Modular QGen is a **component-based framework** for generating high-quality assessment questions with AI assistance. Instead of following a rigid linear process, teachers assemble **6 modular components** into **5 proven workflows** that match their starting context.

**Core Innovation:**
- Not "Phase 1 → 2 → 3" (one path for everyone)
- But "6 components you assemble YOUR way" (context-adaptive)

**Key Features:**
- 🔷 **Dynamic components** = Dialogue-driven (teacher decides)
- 🔶 **Static components** = Checklist-driven (follow specs)
- 🔷🔶 **Hybrid components** = Both dialogue and validation
- ⚡ **5-8 hours** for 40-50 quality questions
- 🎯 **Proven in practice** (Evolution case study: 72 questions)

---

## Quick Start

### 1. Find Your Workflow

Choose the workflow that matches your starting context:

- **Workflow A: Content-Driven** - "I have teaching materials"
- **Workflow B: Standards-Driven** - "I must align to curriculum standards"
- **Workflow C: Question-First** - "I know what I want to ask"
- **Workflow D: Revision-Driven** - "I have old assessments to improve"
- **Workflow E: Technical-First** - "I'm migrating to new LMS"

[See decision tree in docs/00_Framework_Overview.md]

### 2. Read the Framework

Start with the core framework document:

📖 **[docs/00_Framework_Overview.md](docs/00_Framework_Overview.md)** - Complete framework documentation

### 3. Explore Components

Each component has detailed documentation:

- [Component 1: Content Analysis](docs/01_Component_Content_Analysis.md)
- [Component 2: Assessment Design](docs/02_Component_Assessment_Design.md)
- [Component 4: Question Generation](docs/04_Component_Question_Generation.md)
- [Universal QTI Input Specification](docs/07_UNIVERSAL_QTI_INPUT_SPEC.md)

*Note: Components 3, 5, and 6 are described in the main framework document and will be extracted in future versions.*

### 4. See Real Example

📖 **[examples/Evolution_Case_Study.md](examples/Evolution_Case_Study.md)** - Complete implementation walkthrough

---

## Documentation Structure

```
modular-qgen/
├── README.md              # ← You are here
├── LICENSE                # CC BY 4.0 International
├── CHANGELOG.md           # Version history
│
├── docs/                  # Core framework documentation
│   ├── 00_Framework_Overview.md
│   ├── 01_Component_Content_Analysis.md
│   ├── 02_Component_Assessment_Design.md
│   ├── 04_Component_Question_Generation.md
│   └── 07_UNIVERSAL_QTI_INPUT_SPEC.md
│
├── examples/              # Case studies and walkthroughs
│   └── Evolution_Case_Study.md
│
└── archive/               # Previous versions and process docs
    ├── v2.0/
    └── process_documentation/
```

---

## The 6 Components

| Component | Type | Time | Purpose |
|-----------|------|------|---------|
| **1. Content Analysis** | 🔷 DYNAMIC | 1-2h | Understand what was taught |
| **2. Assessment Design** | 🔷 DYNAMIC | 1-2h | Define what to assess |
| **3. Technical Setup** | 🔶 STATIC | 30min | Configure metadata |
| **4. Question Generation** | 🔷🔶 HYBRID | 2-4h | Create questions |
| **5. Quality Assurance** | 🔷🔶 HYBRID | 1h | Validate quality |
| **6. Export/Integration** | 🔶 STATIC | 30min | Convert & import |

**Legend:**
- 🔷 **DYNAMIC** = Dialogue-driven, teacher makes decisions
- 🔶 **STATIC** = Checklist-driven, follow specifications
- 🔷🔶 **HYBRID** = Both dialogue and checklist elements

---

## Who is This For?

**Primary audience:**
- Teachers creating assessments with AI assistance
- Instructional designers building question banks
- Educational developers implementing QTI workflows

**Prerequisites:**
- Access to AI assistant (Claude, ChatGPT, etc.)
- Basic understanding of assessment design
- Target platform: Inspera (or other QTI-compatible LMS)

---

## Version History

**Current version:** 0.0.1 (2025-11-04)

See [CHANGELOG.md](CHANGELOG.md) for complete version history.

**Previous versions:**
- v3.0: Component Architecture (current framework basis)
- v2.0: Process-based approach (archived)

---

## License

This framework is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).

**You are free to:**
- Share — copy and redistribute the material
- Adapt — remix, transform, and build upon the material
- Use commercially

**Under the following terms:**
- Attribution — You must give appropriate credit

---

## Contributing

This is an early-stage framework (v0.0.1). Feedback and suggestions are welcome!

**Ways to contribute:**
- Try the framework and share your experience
- Report unclear sections or gaps
- Suggest improvements or additional workflows
- Share your own case studies

**Contact:** Open an issue on GitHub or reach out via repository discussions

---

## Citation

If you use this framework in your work, please cite:

```
Modular QGen: Modular Question Generation Framework (v0.0.1)
Niklas Karlsson (2025)
Retrieved from: https://github.com/tikankika/Modular-QGen-Framework
```

---

## Acknowledgments

- Developed through practical implementation in Evolution QTI project
- Refined based on teacher workflow analysis
- Built on QTI 2.x standards for assessment interoperability

---

**Status:** Early-stage framework (v0.0.1) - actively developing and refining based on use cases.

**Last Updated:** 2025-11-04
