# AGENTS.md

This repo is a personal learning workspace. Every topic gets a folder. Every folder is a `/teach` workspace. The agent's job is to help Raghu learn deeply — not just cover material, but internalize it through metaphors, visuals, code, and writing.

## Core Workflow

```
User says "I want to learn X"
        │
        ▼
┌─────────────────────────┐
│  1. RESOLVE THE TOPIC   │  Does a folder already exist for X?
│     /raghu-learning     │  Can X be linked to an existing tech stack?
└─────────┬───────────────┘  If neither → create a new folder
          │
          ▼
┌─────────────────────────┐
│  2. SET UP THE WORKSPACE│  Create folder structure, MISSION.md
│     /teach              │  Grill the user on WHY they want to learn this
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  3. BUILD KNOWLEDGE     │  Curate RESOURCES.md, build GLOSSARY.md
│     /domain-modeling    │  Use /ubiquitous-language for terminology
│     /ubiquitous-language│  Cross-link to related topic folders
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  4. CREATE LESSONS      │  Each lesson = one HTML file in ./lessons/
│     /teach              │  Heavy on metaphors, visuals, code snippets
│     /raghu-learning     │  Every lesson links to reference docs
└─────────┬───────────────┘
          │
          ▼
┌─────────────────────────┐
│  5. REVIEW & HANDOFF    │  /handoff when session ends
│     /review /handoff    │  /review to check lesson quality
└─────────────────────────┘
```

## Topic Resolution Rules

When the user says "I want to learn X":

1. **Check existing folders** — scan the repo root for a matching folder. If `rust/` exists and the user says "I want to learn Rust generics", use `rust/`.
2. **Link to existing stack** — if the topic is related to an existing folder, nest or link. "I want to learn Tokio" → goes inside `rust/` since Tokio is part of the Rust ecosystem. Add a cross-reference in the parent folder's `RESOURCES.md`.
3. **Create new folder** — if no connection exists, create a new top-level folder named after the topic in kebab-case (e.g., `distributed-systems/`, `kubernetes/`).

The agent MUST always call `/raghu-learning` first to resolve the topic before starting any teaching.

## Folder Structure

Every topic folder is a `/teach` workspace:

```
<topic>/
├── MISSION.md              # Why this topic matters to Raghu
├── RESOURCES.md            # Curated knowledge sources
├── GLOSSARY.md             # Canonical terminology
├── NOTES.md                # Agent scratchpad for preferences
├── CONTEXT.md              # Domain model (if /domain-modeling is used)
├── learning-records/       # What Raghu has actually learned
│   ├── 0001-first-concept.md
│   └── 0002-second-concept.md
├── lessons/                # The actual lessons (HTML)
│   ├── 0001-intro.html
│   └── 0002-deeper-dive.html
├── reference/              # Compressed cheat sheets (HTML)
│   └── syntax-reference.html
├── assets/                 # Reusable lesson components
│   └── styles.css
└── docs/
    └── adr/                # Architectural decisions (if applicable)
```

## When to Use Each Skill

| Stage | Skill | Purpose |
|-------|-------|---------|
| Topic resolution | `/raghu-learning` | Resolve where the topic lives, link to existing stacks |
| Mission definition | `/grilling` | Interview Raghu on WHY — don't accept vague answers |
| Mission + docs | `/grill-with-docs` | Same as grilling but also builds domain model and ADRs |
| Teaching | `/teach` | The main skill — creates lessons, tracks progress |
| Terminology | `/ubiquitous-language` | Extract and formalize glossary from conversations |
| Domain model | `/domain-modeling` | Build CONTEXT.md, challenge fuzzy language, write ADRs |
| Lesson quality | `/review` | Review a lesson for quality against Raghu's learning style |
| Session end | `/handoff` | Compact the session for the next agent to continue |
| Planning a deep dive | `/to-prd` | Turn a learning goal into a structured plan with user stories |
| Prototyping concepts | `/prototype` | Build throwaway code to test understanding of a concept |

## Agent Rules

1. **Always start with `/raghu-learning`** when the user wants to learn something new. This resolves the topic and sets up the workspace.
2. **Never skip the mission.** If MISSION.md doesn't exist or is vague, use `/grilling` before teaching anything. A bad mission means bad lessons.
3. **Every lesson must have metaphors.** Raghu learns through analogies to things he already knows. If teaching closures, compare them to a backpack. If teaching event loops, compare them to a restaurant kitchen.
4. **Every lesson must have visuals.** Use ASCII diagrams, SVG inline, or mermaid syntax. Text-only lessons are not acceptable.
   - **SVG Quality Standards:** Create SVGs with the polish of an Anthropic technical blog post. Ensure:
     - No overlapping text or elements
     - Proper spacing and padding (minimum 20px between elements)
     - Responsive viewBox that scales cleanly
     - Consistent font families (use system fonts: -apple-system, BlinkMacSystemFont, 'Segoe UI')
     - Color schemes with sufficient contrast (follow WCAG AA standards)
     - Clear visual hierarchy with proper font sizes (titles: 20-22px, subtitles: 14-16px, body: 13px)
     - Use `<defs>` for reusable styles and markers
     - Test that arrows, icons, and annotations don't overlap with main content
     - Include descriptive comments in SVG code
     - Ensure print-friendliness and accessibility
5. **Every lesson must have code snippets.** Even for non-programming topics, express the concept in code when possible. For programming topics, always show runnable examples.
6. **Good writing matters.** Lessons should be concise, well-structured, and a pleasure to read. No walls of text. Use headers, lists, and callouts.
7. **Cross-link topics.** When a lesson touches on a concept from another folder, link to it. The repo is a knowledge graph, not a pile of isolated folders.
8. **Track what's actually learned, not what's covered.** Use learning records for demonstrated understanding only. Coverage is not learning.
9. **Use `/handoff` before ending a session.** The next agent needs to know where things stand.
10. **Respect NOTES.md.** If Raghu expresses a preference ("I hate fill-in-the-blank exercises", "More diagrams please"), record it in NOTES.md and honor it going forward.
