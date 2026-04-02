# AGENTS.md — SAP Architecture Center

This file provides guidance for AI coding agents (e.g., Claude Code, GitHub Copilot, Cursor) working in the **SAP Architecture Center** repository. Follow these instructions when creating, editing, or reviewing content and code in this project.

---

## Project Overview

The **SAP Architecture Center** (https://architecture.learning.sap.com) is an open-source, community-driven documentation site built with **Docusaurus 3**. It publishes **Reference Architectures** — curated, opinionated templates that show how SAP applications, data, and AI services work together at the product and service level, and how organizations can leverage repeatable best practices to optimize SAP cloud and on-premises investments.

The primary audience is **enterprise architects and developers** working with SAP technologies. Content must be accurate, authoritative, and professionally written.

---

## Repository Structure

```
architecture-center/
├── docs/ref-arch/          # Reference architectures (RA0000–RAxxxx)
├── blog/                   # Blog posts
├── community/              # Contributor guidelines and CoP docs
├── src/                    # React components, plugins, theme overrides
├── static/                 # Static assets (images, logos)
├── generator-refArch/      # CLI generator for new reference architectures
├── backend/                # Express/CAP backend services
├── api/                    # API documentation
├── docusaurus.config.ts    # Main Docusaurus config
├── package.json            # Dependencies and scripts
└── CONTRIBUTING.md         # Contributor requirements
```

Each reference architecture lives under `docs/ref-arch/RAXXXX/` and follows this pattern:

```
RAXXXX/
├── readme.md                     # Landing page for the architecture
└── 1-section-name/
    ├── readme.md                 # Section content
    ├── drawio/
    │   └── diagram.drawio        # Editable diagram source
    └── images/
        └── diagram.svg           # Exported SVG (auto-generated from drawio)
```

---

## SAP Brand and Product Names — Spelling Reference

Always use the **exact official capitalization and spelling** for all SAP product and brand names. Never abbreviate, paraphrase, or alter product names without the correct form.

### Core SAP Products and Platforms

| Correct Name | Notes |
|---|---|
| SAP Business Technology Platform (SAP BTP) | Full name first use, then "SAP BTP" |
| SAP S/4HANA | Always uppercase with slash and HANA |
| SAP S/4HANA Cloud, public edition | Lowercase "public edition" |
| SAP S/4HANA Cloud, private edition | Lowercase "private edition" |
| SAP BW/4HANA | Uppercase with slash |
| SAP HANA Cloud | Two words, uppercase HANA |
| SAP Datasphere | One word, capital D |
| SAP Business Data Cloud | Full product name |
| SAP Integration Suite | Two words |
| SAP Integration Suite, advanced event mesh | Lowercase "advanced event mesh" |
| SAP Cloud Application Event Hub | Full product name |
| SAP Event Broker | Two words |
| SAP Cloud Identity Services | Full product name |
| SAP Build | Capital B |
| SAP Build Work Zone | Three words |
| SAP Build Process Automation | Full product name |
| SAP Build Apps | Full product name |
| SAP SuccessFactors | One word, camelCase |
| SAP Ariba | Capital A |
| SAP Concur | Capital C |
| SAP Field Service Management | Full product name |
| SAP Customer Experience (SAP CX) | Abbreviate after first use |
| SAP Commerce Cloud | Full product name |
| SAP Sales Cloud | Full product name |
| SAP Service Cloud | Full product name |
| SAP Joule | Capital J — SAP's AI assistant |
| SAP Joule Studio | Capital J and S |
| SAP Analytics Cloud | Full product name |
| SAP Landscape Transformation Replication Server | Full product name |

### SAP Development Frameworks and Tools

| Correct Name | Notes |
|---|---|
| SAP Cloud Application Programming Model (CAP) | Abbreviate after first use |
| ABAP | Always all caps |
| SAP Fiori | Capital F |
| SAP UI5 | Uppercase, no space before 5 |
| SAP Business Application Studio | Full product name |
| SAP BTP, Kyma runtime | Lowercase "runtime" |
| SAP BTP, Cloud Foundry runtime | Lowercase "runtime" |
| SAP BTP, ABAP environment | Lowercase "environment" |
| Draw.io | Stylized with dot |
| Mermaid | Capital M (diagramming tool) |

### Partner and Hyperscaler Names

| Correct Name | Notes |
|---|---|
| Amazon Web Services (AWS) | Abbreviate after first use |
| Microsoft Azure | Full name or "Azure" |
| Google Cloud Platform (GCP) | Abbreviate after first use |
| Google BigQuery | Capital B and Q |
| Databricks | One word, capital D |
| Snowflake | One word, capital S |
| NVIDIA | All caps |

### Common Mistakes to Avoid

- **Never write**: `S4HANA`, `s/4hana`, `SAP S4/HANA` → **Use**: `SAP S/4HANA`
- **Never write**: `BTP` without `SAP` on first mention → **Use**: `SAP Business Technology Platform (SAP BTP)`
- **Never write**: `Successfactors` or `Success Factors` → **Use**: `SAP SuccessFactors`
- **Never write**: `advanced Event Mesh` or `Advanced Event Mesh` → **Use**: `SAP Integration Suite, advanced event mesh`
- **Never write**: `Datasphere` without `SAP` → **Use**: `SAP Datasphere`
- **Never write**: `CAP framework` → **Use**: `SAP Cloud Application Programming Model (CAP)` or `CAP` after first use
- **Never write**: `Joule` without `SAP` on first mention → **Use**: `SAP Joule`

---

## Writing Style and Tone

### Audience

Write for **enterprise architects and senior developers** who are familiar with SAP technologies. Assume a high level of technical literacy but explain architectural decisions and trade-offs clearly.

### Tone

- **Professional and authoritative** — this is official SAP guidance material
- **Objective and solution-oriented** — focus on value, best practices, and outcomes
- **Neutral and factual** — avoid marketing superlatives ("best-in-class", "revolutionary", "game-changing")
- **Inclusive** — use plain, accessible English; avoid idioms or culturally specific expressions
- **Concise** — prefer clarity over verbosity; avoid filler phrases

### Voice

- Write in **third person** for conceptual descriptions: *"The integration pattern enables..."*
- Use **"we"** sparingly when speaking from the SAP perspective: *"We recommend..."*
- Avoid second person ("you") except in direct instructional steps
- Use **active voice** wherever possible

### What to Avoid

- Marketing language: *"seamlessly", "powerful", "robust", "cutting-edge", "next-generation"*
- Vague claims without technical substance
- Excessive qualifiers: *"very", "quite", "rather", "basically"*
- Colloquialisms or informal language
- Emoji in content articles
- First-person singular ("I think...", "I believe...")

### Preferred Phrasing Examples

| Avoid | Prefer |
|---|---|
| "This powerful solution seamlessly integrates..." | "This solution integrates..." |
| "You can easily connect SAP S/4HANA to..." | "SAP S/4HANA connects to..." |
| "Leverage the cutting-edge capabilities of..." | "Use the capabilities of..." |
| "This is a game-changer for enterprises." | "This approach reduces integration complexity for enterprises." |

---

## Content Structure for Reference Architectures

Every reference architecture `readme.md` should follow this standard structure:

```markdown
---
# front matter (see below)
---

## Overview / Introduction
Brief description of the architectural pattern and its business relevance.

## Architecture
Embed the main drawio diagram:
![drawio](drawio/filename.drawio)

## How It Works / Architecture Flow
Numbered steps describing the data or process flow.

## When to Use
Bullet list of use cases or scenarios where this architecture applies.

## Recommendations / Design Considerations
Key architectural decisions, trade-offs, and best practices.

## Related Resources
Links to SAP documentation, blog posts, or related reference architectures.
```

---

## Front Matter Requirements

Every markdown file must include YAML front matter. Required fields:

```yaml
---
id: id-ra0001                        # Unique: id-<raXXXX> or id-<raXXXX>-<section>
slug: /ref-arch/<unique-hash>         # URL-safe unique slug
sidebar_position: 1
sidebar_custom_props:
  category_index:
    - integration                     # Use only tags from docs/tags.yml
title: Exact Page Title
description: >-
  SEO description, max ~300 characters. Describe the architecture clearly.
keywords:
  - sap
  - relevant-keywords
sidebar_label: Short Sidebar Title
image: img/ac-soc-med.png
tags:
  - integration                       # Use only tags defined in docs/tags.yml
hide_table_of_contents: false
hide_title: false
toc_min_heading_level: 2
toc_max_heading_level: 4
draft: false
unlisted: false
contributors:
  - github-username
last_update:
  author: github-username
  date: YYYY-MM-DD
---
```

**Valid tags** are defined in `docs/tags.yml`. Do not invent new tags; use only the defined taxonomy:
`aws`, `azure`, `gcp`, `ibmcloud`, `databricks`, `nvidia`, `snowflake`, `genai`, `appdev`, `data`, `integration`, `security`, `cap`, `abap`, `eda`, `eic`, `build`, `buildworkzone`, `transition`, `bdc`, `agents`, `ref-arch`, `community`, `demo`

---

## Diagrams

### Draw.io Diagrams
- Always use the [SAP BTP Solution Diagram Starter Kit](https://experience.sap.com/fiori-design-web/solution-diagram/) for technical architecture diagrams
- Store editable sources in `drawio/` subdirectory
- Embed in markdown: `![drawio](drawio/filename.drawio)`
- Do not embed raw SVG or PNG unless the drawio approach is not applicable
- The site renders drawio files inline with download and online-edit options

### Mermaid Diagrams
- Use for **process flows**, **sequence diagrams**, and **decision trees**
- Use fenced code blocks with the `mermaid` language identifier
- Keep diagrams simple and readable; break complex flows into multiple diagrams

---

## File and Folder Naming Conventions

- Reference architecture folders: `RAXXXX/` (four-digit zero-padded number)
- Section folders: `1-descriptive-name/`, `2-descriptive-name/` (numbered, lowercase, hyphens)
- All markdown files: `readme.md` (lowercase)
- Drawio files: `kebab-case-description.drawio`
- Images: `kebab-case-description.svg` or `.png`
- Blog posts: `YYYY-MM-DD-slug-title.md`

---

## Code Formatting Standards

Enforced via Prettier. When modifying TypeScript/JavaScript/MDX:

- **Tab width**: 4 spaces
- **Semicolons**: required
- **Single quotes**: yes
- **Trailing comma**: ES5 style
- **Print width**: 120 characters
- **Line endings**: LF
- **Arrow function parens**: always

Run `npm run format` before committing code changes.

---

## Custom React Components

The following custom components are available in MDX content:

| Component | Usage |
|---|---|
| `![drawio](path)` | Renders an editable Draw.io diagram |
| `contributors:` front matter | Renders contributor acknowledgement block |
| Standard admonitions | `:::tip`, `:::note`, `:::warning`, `:::info`, `:::danger` |
| Mermaid diagrams | ` ```mermaid ` fenced code block |

Do not create ad-hoc inline HTML or import external React components in content markdown. Use only the established component patterns.

---

## What Agents Should NOT Do

- **Do not invent SAP product names** or use unofficial abbreviations
- **Do not remove or alter front matter fields** without understanding their purpose
- **Do not change tags** to values not present in `docs/tags.yml`
- **Do not create new folders** without following the `RAXXXX/N-section-name/` naming convention
- **Do not add marketing language** or unsubstantiated claims to content
- **Do not commit secrets**, credentials, API keys, or personal data
- **Do not push directly to `main` or `dev`** — always work in feature branches
- **Do not skip CI checks** — the `spelling.yml` workflow validates content spelling
- **Do not remove `LICENSES/` headers** — the project uses REUSE compliance tooling
- **Do not use emoji** in documentation content

---

## Common Agent Tasks and How to Approach Them

### Adding a New Reference Architecture
1. Run `npm run gen-ref-arch` and follow the interactive CLI (`genrefarch`)
2. The generator creates correct folder structure and template files automatically
3. Fill in front matter with valid tags from `docs/tags.yml`
4. Replace placeholder text with real content following the structure above
5. Add a drawio diagram using the SAP BTP Solution Diagram Starter Kit

### Reviewing or Editing Existing Content
1. Check SAP product name spelling against the table in this file
2. Verify front matter completeness and valid tag values
3. Ensure tone is professional and avoids marketing language
4. Confirm diagram files exist in `drawio/` and are referenced correctly
5. Validate that `last_update.date` is updated and contributor is listed

### Spell-Checking SAP Brand Names
Use the reference table in this file. The CI pipeline also runs `spelling.yml` — do not suppress or bypass this check. If adding a new SAP product name that triggers a false positive, update the `.wordlist.txt` or equivalent spelling configuration rather than skipping the check.

### Writing Blog Posts
- Location: `blog/YYYY-MM-DD-slug.md`
- Author must be registered in `blog/authors.yml`
- Follow the same tone and brand name guidelines as reference architecture content
- Blog posts may be slightly more narrative but must remain professional

---

## AI-Generated Content Policy

This project follows SAP's [guideline for AI-generated code contributions](https://github.com/SAP/.github/blob/main/CONTRIBUTING_USING_GENAI.md). When using AI assistance:

- All AI-generated content must be **reviewed and verified** by a human contributor before merging
- Contributors remain **fully responsible** for the accuracy of submitted content
- AI-generated content must comply with the **Developer Certificate of Origin (DCO)**
- SAP product names, version numbers, and technical claims must be **manually verified** — do not trust AI-generated product names without cross-checking against this file and official SAP documentation

---

## Key Links

- Live site: https://architecture.learning.sap.com
- GitHub repository: https://github.com/SAP/architecture-center
- SAP BTP Solution Diagram Kit: https://experience.sap.com/fiori-design-web/solution-diagram/
- Contributor guidelines: `community/02-Guidelines/01-contribution.md`
- Front matter reference: `community/02-Guidelines/04-front-matter.md`
- Content structure guide: `community/02-Guidelines/03-content-structure.md`
- Diagram guide: `community/02-Guidelines/06-diagrams.md`
- Tag definitions: `docs/tags.yml`
