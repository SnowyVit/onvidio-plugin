---
name: create-video-influence
description: Trigger this skill when the user asks to turn a LinkedIn post into a video, create a thought leadership piece, or share an industry news reaction.
---

# Influence Pillar Playbook (Personal Branding)

This pillar handles videos designed to build authority, share insights, and grow an audience. The tone should be authentic, opinionated, and fast-paced (optimized for social feeds like LinkedIn and Shorts).

## 🎬 Leading & Closure Framing

Every influence video must bookend its narrative with social authority and engagement:

### 1. The Leading Scene (The Polarizing Claim / Contrarian Hook)
* **Concise & Immediate:** Spoken narration must be **strictly 15–25 words max**. Hook feed-scrollers within 3 to 5 seconds with a bold, provocative assertion.
* **Category Eyebrow:** E.g., `PERSPECTIVE`, `HOT TAKE`, `UNPOPULAR OPINION`.

### 2. The Closure Scene (The Engagement Prompt / Takeaway)
* **Punchy & Decisive:** Spoken narration must be **strictly 10–20 words max**. Pose a conversation-starting question to drive comments and community discussion.
* **Category Eyebrow:** E.g., `THE TAKEAWAY`, `WHAT'S YOUR TAKE`, `JOIN THE DISCUSSION`.

## 🏗️ Extensibility Guide
To add a new topic to this pillar:
1. Create a new `### Topic: [Name]` section below with trigger words.
2. Define its scene-by-scene narrative structure.
3. Ensure **Scene 1** adheres to the concise Polarizing Hook (15–25 words max).
4. Ensure the **Final Scene** delivers the concise Engagement Prompt / Takeaway (10–20 words max).

## 📚 Topics

> **Dynamic Layout Selection:** Do not force scenes into a rigid structure. For each scene, actively collaborate with the user or use your best judgment to determine the optimal layout `type` (`description`, `quote`, or `bullet_points`) based on the specific content and flow of the video. Ensure the drafted content naturally fits the chosen type while retaining enough detail for the alternative fields.

### Topic: Thought Leadership / LinkedIn Insight
**Trigger Words:** insight, thought leadership, linkedin post, my opinion on
**Narrative Structure:**
1. **Scene 1: The Bold Claim** - A polarizing or interesting statement (e.g., "Most startups fail because they hire too fast").
2. **Scene 2: The Breakdown** - The 3 rules or reasons supporting the claim.
3. **Scene 3: The P.S. Takeaway** - A final thought or question for the audience to engage in the comments.

### Topic: Build in Public
**Trigger Words:** build in public, update, indie hacker, micro-saas
**Narrative Structure:**
1. **Scene 1: The Goal** - What you tried to achieve today.
2. **Scene 2: The Struggle / Code** - The reality of the process.
3. **Scene 3: The Result / Metrics** - Revenue gained, users added, or bugs fixed.

### Topic: Industry News React
**Trigger Words:** news react, breaking news, hot take
**Narrative Structure:**
1. **Scene 1: The News** - Quote the headline or the event.
2. **Scene 2: Why it Matters** - The context.
3. **Scene 3: My Take** - 2 or 3 predictions on what happens next.

## 🛑 MANDATORY SCHEMA ENFORCEMENT
Once you have finalized the narrative and scene structure based on the chosen topic above, you **MUST** format the final output using the strict rules and schema defined in the `create-video` skill. You cannot output raw text; you must hand off to the `create-video` compiler to generate valid Onvidio JSON.
