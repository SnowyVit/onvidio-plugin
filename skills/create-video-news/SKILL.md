---
name: create-video-news
description: Trigger this skill when the user asks to create a news report, breaking news dispatch, daily news digest, multi-story rundown, market update, investigative brief, or current affairs explainer.
---

# News Pillar Playbook (Journalism & Current Affairs)

This pillar handles videos designed to inform the public, break down current events, and deliver fact-checked, objective journalism. The tone must be authoritative, impartial, urgent, and credible.

---

## 🎙️ Broadcast Newsroom Standards

When scripting and structuring news videos, you must adhere to the standards of an experienced broadcast news producer and investigative reporter:

### 1. The Inverted Pyramid & Attribution-First
* **The Lede Comes First:** Never bury the lede. Scene 1 must immediately answer: *Who, What, When, Where,* and the immediate *Why*.
* **Attribution-First:** In broadcast journalism, always cite the source *before* making the assertion (*"According to the Labor Department..."*, *"Federal prosecutors allege..."*, rather than placing the attribution at the end of a sentence).
* **Objective & Active Voice:** Avoid emotional hyperbole or marketing adjectives ("shocking", "game-changing", "exciting"). State the verifiable facts plainly with active, present-tense verbs (*"Regulators investigate"*, *"Shares tumble"*, *"Diplomats convene"*).

### 2. Writing for the Ear (Audio Copywriting)
* **Sentence Length:** Keep sentences in `narration` between 10 and 18 words max. Punctuate for natural breathing pauses.
* **Ear-Friendly Numbers:** Round large numbers in spoken copy (*"nearly three billion dollars"*, not *"$2,981,420,120"*; *"roughly one in four"* instead of *"24.7%"*). Keep the exact numbers in the on-screen `features` array.
* **Avoid Phonetic Clutter:** Avoid acronyms unless universally recognized (use *"The Environmental Protection Agency"* on first mention before *"EPA"*).

### 3. Audio-Visual Handshake (No Verbatim Recital)
* **The On-Screen Graphics (`title`, `features`, `quote`):** Act as the broadcast **Chyron / Lower-Third / Info-Graphic**. They anchor hard data points, dates, job titles, and concise bullet points.
* **The Spoken `narration`:** Carries the human storytelling, context, and meaning. It must **NEVER** recite the on-screen text word-for-word.

### 4. The Unbroken Narrative Thread (Scene-to-Scene Flow)
A news broadcast is not a deck of isolated slides. **The spoken narration must maintain an audible throughline from scene to scene.** Every scene $N+1$ MUST use a connective verbal bridge from scene $N$:
* **Cause & Effect Bridge:** *"That sudden shift triggered an immediate wave of regulatory scrutiny..."*
* **Perspective / Contrast Bridge:** *"While corporate leadership defended the restructuring, labor representatives painted a starkly different picture..."*
* **Zoom-Out (Systemic) Bridge:** *"This is not an isolated incident—it reflects a broader trend rippling across..."*
* **Timeline Bridge:** *"Before reaching this tipping point, negotiations had stalled for months over..."*
* **Horizon Bridge:** *"The immediate focus now shifts to Capitol Hill, where lawmakers are scheduled to..."*

---

## 🎬 Leading & Closure Framing

Every news video must bookend its narrative with journalistic framing:

### 1. The Leading Scene (The Lede / Cold Open)
* **Concise & Immediate:** Spoken narration must be **strictly 15–25 words max**. Hook the viewer within the first 3 to 5 seconds with zero throat-clearing.
* **Strictly Prohibited:** Never use generic internet or marketing greetings (e.g., *"Hey everyone, welcome back"*, *"Today we're talking about..."*).
* **Broadcast Cold Open:** Open immediately with a dateline and the breaking development (*"WASHINGTON — Federal Reserve officials announced today..."*).
* **Category Eyebrow:** Set `category` to an uppercase news slug (e.g., `BREAKING NEWS`, `DEVELOPING`, `MARKET ALERT`, or a dateline like `BRUSSELS — 08:00 CET`).

### 2. The Closure Scene (The Kicker & Sign-Off)
* **Punchy & Decisive:** Spoken narration must be **strictly 10–20 words max**. Deliver a definitive, authoritative closing without trailing off.
* **Strictly Prohibited:** Never use commercial calls-to-action (e.g., *"Like and subscribe"*, *"Try it free"*, *"Click the link below"*).
* **The Analytical Kicker:** What the situation hinges on next (*"Whether these measures stabilize fuel prices will depend on the upcoming OPEC summit."*).
* **The Milestone Watch:** When the next official update, vote, or press briefing takes place (*"The Senate Banking Committee is scheduled to hear testimony on Thursday morning."*).
* **Broadcast Sign-Off:** Close with professional newsroom sign-off copy (*"We will continue monitoring this story. Stay with Onvidio News for ongoing updates."*).

---

## ⏱️ Duration & Pacing Presets

Anchor speech rate is approximately **130–150 words per minute (WPM)** (~2.2 words per second). Match the scene count and word count to the user's requested format:

* **Short News Flash / Social Reel (30s – 60s):**
  * **Scenes:** 3 to 4 scenes total.
  * **Narration Word Count:** ~100 – 130 words total (~25–35 words per scene).
  * **Focus:** 1 single breaking development or up to 3 rapid-fire headline cards.
* **Standard News Bulletin (60s – 90s):**
  * **Scenes:** 4 to 5 scenes total.
  * **Narration Word Count:** ~140 – 200 words total.
* **3-Minute In-Depth Broadcast Package (2.5 – 3 minutes):**
  * **Scenes:** 8 to 12 scenes total (within Onvidio's 15-scene hard cap).
  * **Narration Word Count:** ~380 – 450 words total.
  * **Structure:** Classic 3-Act broadcast architecture:
    * *Act I (Scenes 1–3):* The Lede, Nut Graph, and Immediate Stakeholder Impact.
    * *Act II (Scenes 4–7):* Deep Background, Key Data Breakdown, Official Statement (Quote 1), and Counter-Response (Quote 2).
    * *Act III (Scenes 8–10+):* Systemic Consequences, Milestone Watch, and Reporter Sign-Off.

---

## 📰 Multi-Story Digest & Editorial Curation (The Rundown)

When the user provides multiple news stories, raw wire feeds, or requests a "Daily Roundup / News Briefing":

### 1. Capacity Limits
* **60-Second Short Digest:** Curate **1 to 3 stories max** (3–4 scenes total).
* **3-Minute News Digest:** Curate **4 to 7 stories max** (10–14 scenes total).

### 2. Editorial Triage Protocol (When provided with > 7 stories)
If the user inputs 8 or more stories, act as the **Executive News Producer** and prune the list:
1. **Prioritize High-Value News:**
   * Systemic economic impact, legislative/regulatory actions, major market shocks, public safety, and institutional accountability.
2. **Spike / Discard Low-Value Items:**
   * Routine corporate PR releases, minor marketing announcements, incremental software version updates, and unverified rumors.
3. **Sequence the Broadcast Lineup:**
   * **Story 1 (The Lead Story):** The most critical, high-impact headline.
   * **Stories 2–4 (Core Developments):** Major business, policy, or international developments.
   * **Stories 5–6 (Industry/Trends):** Tech breakthroughs or sector shifts.
   * **Final Story (The Kicker):** An inspiring human interest, scientific, or forward-looking story before sign-off.

### 3. Inter-Story Verbal Bridges
Transitions between distinct stories in narration must use natural broadcast pivots:
* **Thematic Pivot:** *"Turning from domestic policy to Wall Street, markets saw sharp swings today as..."*
* **Geographic Pivot:** *"Meanwhile overseas, European regulators took decisive action against..."*
* **Contrast Pivot:** *"While enterprise revenues beat expectations, consumer sentiment told a different story..."*
* **Rapid-Fire Pivot:** *"In other business developments this morning..."*
* **The Final Kicker Pivot:** *"And finally tonight, researchers at MIT have unveiled..."*

## 🏗️ Extensibility Guide
To add a new topic to this pillar:
1. Create a new `### Topic: [Name]` section below with trigger words.
2. Define its scene-by-scene narrative structure.
3. Ensure **Scene 1** adheres to the concise Leading Scene (Cold Open Lede, 15–25 words max).
4. Ensure the **Final Scene** delivers the concise Closure Scene (Kicker / Sign-Off, 10–20 words max).

---

## 📚 Topics

> **Dynamic Layout Selection:** For each scene, actively select the layout `type` (`description`, `quote`, or `bullet_points`) that best reflects the broadcast goal. Every scene must still populate high-quality alternative fields (`subtitle`, `features`, `quote`) so users can switch layout styles seamlessly in the editor.

---

### Topic: Breaking & Developing News
**Trigger Words:** breaking news, bulletin, urgent dispatch, developing story, press conference  
**Scene Count:** 4–5 Scenes (~60–90s)  
**Narrative Structure:**
1. **Scene 1: The Lede (The Cold Open)**  
   * *Type:* `description`  
   * *Category:* `BREAKING NEWS` or `DEVELOPING`  
   * *Content:* What happened, who is involved, dateline, and immediate facts.
2. **Scene 2: The Stakes (Nut Graph)**  
   * *Type:* `description` or `bullet_points`  
   * *Category:* `WHY IT MATTERS`  
   * *Bridge:* Explains why the event has immediate public, market, or legal significance.
3. **Scene 3: Key Evidence & Details**  
   * *Type:* `bullet_points`  
   * *Category:* `THE DETAILS`  
   * *Bridge:* Timeline, figures, or specific regulatory provisions.
4. **Scene 4: Official Reaction / Soundbite**  
   * *Type:* `quote`  
   * *Category:* `OFFICIAL RESPONSE`  
   * *Bridge:* Direct quote from a spokesperson, agency official, or CEO.
5. **Scene 5: Developing Outlook (The Kicker)**  
   * *Type:* `description`  
   * *Category:* `DEVELOPING WATCH`  
   * *Bridge:* Next milestone, scheduled hearings, and newsroom sign-off.

---

### Topic: Multi-Story News Digest / The Rundown
**Trigger Words:** daily brief, news digest, top stories, news roundup, weekly recap, the rundown  
**Scene Count:** 4–5 Scenes (60s short, 1–3 stories) OR 10–14 Scenes (3min package, 4–7 stories)  
**Narrative Structure:**
1. **Scene 1: Anchor Lead-In & Story 1 (Top Headline)**  
   * *Type:* `description`  
   * *Category:* `TOP STORY`  
   * *Content:* Anchor introduces today's top development with urgency.
2. **Scenes 2 to N-1: Sequential Story Blocks**  
   * *Type:* Alternate between `bullet_points` (for metrics/facts) and `description` or `quote`.  
   * *Category:* Sector or topic tags (`ECONOMY`, `GLOBAL`, `TECH REGULATION`, `ENERGY`).  
   * *Bridge:* Connect each story with natural journalistic transitions (*"Turning to...", "Meanwhile..."*).
3. **Final Scene: The Kicker Story & Newsroom Sign-Off**  
   * *Type:* `description`  
   * *Category:* `FINAL TAKE` or `SIGN-OFF`  
   * *Bridge:* Closing story plus anchor sign-off and next broadcast cue.

---

### Topic: News Analysis & Deep Dive (WSJ / Bloomberg Style)
**Trigger Words:** news analysis, deep dive, explainer, investigative report, policy breakdown  
**Scene Count:** 6–10 Scenes (2–3 minutes)  
**Narrative Structure:**
1. **Scene 1: The Core Conflict / Mystery** - The central paradox or question in current affairs.
2. **Scene 2: Historical Context & Timeline** - How the situation arrived at this point.
3. **Scene 3: The Data & Mechanism** - `bullet_points` breaking down the numbers.
4. **Scene 4: Stakeholder Impact** - Real-world impact on consumers, workers, or companies.
5. **Scene 5: Verified Voice #1 (Proponent / Regulator)** - `quote` with attributed official statement.
6. **Scene 6: Verified Voice #2 (Critic / Counter-Argument)** - `quote` showing the opposing view.
7. **Scene 7: Long-Term Consequences & Kicker** - What this means for the industry moving forward.

---

### Topic: Business & Financial Dispatch
**Trigger Words:** market update, earnings dispatch, stock plunge, macroeconomic news, fed rate, merger  
**Scene Count:** 4–6 Scenes (~60–120s)  
**Narrative Structure:**
1. **Scene 1: The Market Move** - Topline index movement, earnings surprise, or merger announcement.
2. **Scene 2: Core Revenue & Margin Drivers** - `bullet_points` breaking down the key metrics.
3. **Scene 3: Executive or Wall Street Soundbite** - `quote` with CEO or chief analyst reaction.
4. **Scene 4: Supply Chain & Sector Ripple** - How competitors or macro trends are influenced.
5. **Scene 5: Trading Ahead & Forward Guidance** - Upcoming Fed data, earnings calls, or market open forecast.

---

## 🛑 MANDATORY SCHEMA ENFORCEMENT
Once you have finalized the narrative, script, and scene flow based on the journalistic standards above:
1. You **MUST** format the final output using the strict schema defined in the `create-video` skill (`references/schema.md`).
2. Populate all required text fields (`category`, `title`, `subtitle`, `features`, `narration`, `mediaSearchQuery`).
3. If `quote` is used, ensure `author` is accurately credited.
4. Hand off to the `create-video` compiler to produce valid Onvidio JSON.
