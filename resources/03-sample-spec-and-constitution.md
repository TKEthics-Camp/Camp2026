# PRD — The Signal: a newsreader for young students

**Status:** Clickable demo (v2) · **Owner:** TKEthics · **Last updated:** July 2026

## 1. Problem

Young students (middle/high school) are surrounded by news but rarely engage
with it: adult news is too dense, social feeds are algorithmic and unsourced,
and nothing connects current events to their own lives or classrooms. They
graduate news-illiterate — unable to name sources, spot bias, or explain why an
event matters.

## 2. Goals

1. Help students **understand what's happening** in the real world, daily.
2. **Connect events to their lives** — every story answers "why does this
   matter to *me*?"
3. Expose **different perspectives** and teach source/bias awareness.
4. Get students to **question their own assumptions** (reason before results).
5. Let them **share what's worth sharing** with their class community.
6. (v2) Support **bilingual reading (EN/中文)** and lightweight **vocabulary
   learning** in context.

**Non-goals:** breaking news speed; comprehensive coverage; open social
network (community = the student's own class); gamification points/streaks.

## 3. Audience

- Primary: students ~11–16, reading on phones, short attention windows.
- Secondary: teachers who seed discussion from the day's stories and polls.

## 4. Product shape

A mobile, story-a-screen swipeable feed. **3 stories per day + 1 recap card.**
Deliberately finite — "done for today" is a feature.

### 4.1 Story card (the core unit)

- **Hook** — one arresting sentence.
- **Fact** — the story in ≤3 sentences, concrete numbers.
- **Why it matters to you** — explicit reframe to the student's life.
- **Source + lean label** — e.g. "Reuters · International wire service".
  Always visible; this is the media-literacy layer.
- **Lens tag** — each story is tagged Social currency / Your money / The
  bigger picture, so the day covers different ways news touches a life.
- Actions: **Go deeper** (bottom sheet) and **Share**.

### 4.2 Go-deeper sheet (per story)

- **Background** — the one concept you need (e.g. what a tariff is).
- **Two Sides** — strongest honest version of each camp's argument.
- **Poll** — three-step flow, in this order, non-negotiable:
  1. Vote (no results visible)
  2. Explain your reasoning in one sentence (skippable, but asked)
  3. Reveal class results + your reasoning back to you
  Rationale: committing and articulating *before* seeing the majority
  counters conformity bias. Never collapse to instant-reveal.
- **Class** — classmates' takes; agree (👍) or add your own.

### 4.3 Community layer

- Share a story with **your take attached** to class or a friend.
- "N classmates read this" on each card.
- Recap card shows **class pulse**: takes shared, votes cast, and the most
  contested poll ("worth bringing up tomorrow") — bridges app → classroom
  discussion.

### 4.4 Recap card

"You can now explain: …" — restates the day as competence, not consumption.
Ends with one-tap reflection and "come back tomorrow."

### 4.5 Bilingual + vocabulary (v2)

- 中文/EN toggle in the header; translates all content and UI. Persisted.
- **Curated glossary** per story (not a full dictionary): key terms get dotted
  underlines; hover/tap shows meaning, pronunciation (respelling or pinyin),
  and text-to-speech. User-generated takes stay in their original language.

## 5. Tone & design principles

- Talk *with* students, not down: real numbers, real stakes, no babying.
- Warm print-like feel (paper background, serif hooks) — calmer than a
  social feed, friendlier than a newspaper.
- Sentences short; vocabulary hard words glossed, not avoided.
- No infinite scroll, no engagement dark patterns.

## 6. Current state (this demo)

Static HTML/CSS/JS, no backend. All stories, poll percentages, classmate
takes, and class stats are **mock data**. Language choice persists via
localStorage; everything else resets on reload.


## 7. Decisions & next steps


- **Content pipeline (decided):** editors hand-pick ~3 stories per week; AI
  adapts each story per student — grade level, reading interests, and
  vocabulary level (including which glossary words to surface).
- **Accounts, rosters & moderation (decided):** Google Sheets as the
  lightweight backend for rosters and shared takes; teacher moderates via the
  sheet. Revisit when scale demands a real backend.
- **Teacher view (next up):** a web portal for teachers — seed polls, see
  class pulse, review/moderate takes, export discussion prompts.
- **Accessibility:** deferred for now.
- **Poll-flow validation:** pilot with a real class to confirm students engage
  with the "explain your reasoning" step rather than skipping it; rework the
  flow if skip rate is high.

