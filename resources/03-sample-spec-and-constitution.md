# Sample Spec & Constitution — "ClearNews"

A worked example. **A model to imitate, not to copy.** Your product is not this product.

---

# Part 1 · The Constitution

Seven rules. Each one traceable to an ethical lens. Imperative, specific, checkable.

A Constitution is not a values statement. It is a list of things your product may
**never** do — written so that a machine, or a classmate, can check whether you broke one.

### ClearNews Constitution

1. **We optimise for understanding, not time-on-app.** No streaks, no infinite scroll,
   no notifications. *(consequences)*

2. **We collect no personal data from a child.** First names or codes only — never a
   real identity. *(rights)*

3. **Every story shows where it came from.** No naked claims. *(rights)*

4. **A glossary entry never uses a harder word to explain a hard word,** and never
   carries an opinion. *(virtue)*

5. **The AI may only explain a word that actually appears in the story.** It never
   invents a term, and if it does not know what a word means here, it writes
   `NEEDS HUMAN` rather than guessing. *(rights)*

6. **The AI proposes; a human decides.** No glossary entry reaches a student until a
   person has approved it. *(rights)*

7. **Every student's take is their own.** The AI never writes a student's opinion for
   them. *(virtue)*

> **Why Article 7 matters most:** this product exists to make children think, not to
> think for them. It is also the most interesting one for the red team to attack.

---

# Part 2 · The Spec

**ClearNews — one-page spec**

### 1. Problem

Rural middle-schoolers want to follow world events, but the news is written for adults
in English they cannot yet read — and they almost never get asked what they think
about it.

*(Day 2 evidence: students said they "don't understand the words"; wish wall:
"I hope AI can explain the news to us.")*

### 2. Users

Students aged 11–14 at ___ school, using a shared computer in the Zhong Gu classroom.
Slow connection, English is a second language, little prior tech exposure.

### 3. The one thing it does

Shows three short news stories a day, with the hard words explained — and lets a
student say what they think.

### 4. What it must remember

For each story: the text, where it came from, and which words were explained and how.
For each student: which stories they voted on, and what they wrote.

*(Plain English. The tables get named on Day 4, in the Plan.)*

### 5. Guardrails

See the Constitution, above.

### 6. Out of scope (v1)

No accounts, no feed, no notifications, no recommendation algorithm, no
personalisation, no audio.

### 7. Success test

A student at ___ school, with nobody helping, reads one story, can say what happened,
votes, and writes one sentence of their own.

---

## How to use this example

**Do:** copy the *shape* — seven short sections, one page, plain language, a success
test someone could actually run.

**Don't:** copy the content. If your spec says "plain-language news reader" and your
team spent Day 2 hearing about something else entirely, you wrote down our idea
instead of your evidence.

**The test:** every claim in section 1 should be traceable to something a real person
said to you on Day 2.
