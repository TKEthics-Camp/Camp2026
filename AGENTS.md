# AGENTS.md

Instructions for any AI coding tool (Claude Code, Cursor, etc.) working in this repo.

This is the public course homepage for AI Product Camp 2026 (TKEthics × WeUp × Zhong Gu Foundation).
The main file is `index.html` — a single-page, bilingual (EN/ZH) site using `lang="en"` / `lang="zh"`
spans toggled by `#langToggle`. Each `<details>` block under "Daily notes" covers one camp day and
always has matching English and Chinese `<div lang="en">` / `<div lang="zh">` content.

## Style guide

### Bolding in Daily notes

Only two kinds of things get bolded in each day's `Objectives` and `Process` sections — nothing else.

1. **Knowledge/skills being taught.** In `Process` bullets, rewrite the lead-in as a short question
   whose answer is the thing being learned, and bold the question — e.g. "what is vibe coding?",
   "how does hallucination happen?". Use whichever question word fits naturally (what/how/why);
   "what is X?" is the default for a plain term or concept.
   - Only bold this in `Process` bullets that are lectures/demos actually teaching a defined
     concept — not activity/workshop bullets with no concrete concept stated in the bullet itself
     (e.g. "Icebreaker," "Guided ethics review," "Ethics case writing workshop").
   - If one bullet bundles multiple distinct taught concepts, bold only the single main concept as
     one question; leave the rest of the bullet as unbolded supporting detail. Don't split the
     bullet, and don't add a second bolded question to it.
   - Don't force this rewrite in `Objectives` paragraphs (prose, not bulleted lecture lines) — see
     rule 2 for how `Objectives` gets bolded.
2. **Deliverables** — concrete artifacts students walk away with (e.g. a GitHub repo, a PRD, a
   Constitution, a live URL, a clickable demo, a working feature, a recorded interview, a Developer
   Log entry, an ethics case). Bold the noun phrase as-is, not as a question. This applies in both
   `Process` and `Objectives`. A bullet/sentence can bold more than one deliverable noun if more
   than one is named.
   - Milestone/gate events that aren't a physical artifact (e.g. "code freeze," "ship gate") are
     NOT bolded under this rule, even though they're important moments.
   - The output of a synthesis/discussion moment (e.g. "turn what you saw into product decisions")
     is NOT a deliverable — nothing gets saved as a distinct artifact at that point, it just feeds
     into a later one (e.g. the PRD). Don't bold these even though they're real outcomes of the day.

Nothing else gets bolded: not activity/session labels ("Icebreaker," "Round-robin," "Blind test" as
a label), not emphasis words, not award names.

### Bolding in the concluding callouts

Each day's Process list is followed by a one-paragraph callout (e.g. "Line of the day," "Mindset,"
"The most important sentence today," "Your Constitution goes to work," "The best experiment of the
week," "An honest closing," "The rule"). This is a separate rule from the Process/Objectives one
above. Bold exactly **one** clause or sentence per callout — the single most important one:

- If the callout contains a quotation-marked line, that's generally where the important clause
  lives — bold it. If the quote spans multiple sentences, bold only the single sharpest one, not
  the whole quote.
- Otherwise, bold whichever single sentence most broadly summarizes the day's main point — the
  takeaway insight itself, not a supporting instruction or scene-setting detail around it.

Never bold the whole paragraph, never bold more than one sentence, and don't mix in italics or any
other emphasis alongside the bold.
