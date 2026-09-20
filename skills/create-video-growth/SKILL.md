---
name: create-video-growth
description: Trigger this skill when the user asks to create a promotional video, commercial, product launch, sales proposal, cold outreach, or investor pitch.
---

# Growth Pillar Playbook (Sales & Marketing)

This pillar handles videos designed to persuade the viewer, generate leads, and close deals. The tone should be high-energy, ROI-focused, and visually engaging.

## 🎬 Leading & Closure Framing

Every growth video must bookend its narrative with high-conversion framing:

### 1. The Leading Scene (The Pain-Point / Value Hook)
* **Concise & Immediate:** Spoken narration must be **strictly 15–25 words max**. Hook the viewer within the first 3 to 5 seconds by introducing the core pain point or bold promise.
* **Category Eyebrow:** E.g., `THE PROBLEM`, `INTRODUCING`, `NEW FEATURE`.

### 2. The Closure Scene (The Call to Action)
* **Punchy & Decisive:** Spoken narration must be **strictly 10–20 words max**. Provide a single, friction-free action.
* **Category Eyebrow:** E.g., `GET STARTED`, `FREE TRIAL`, `NEXT STEPS`.

## 🏗️ Extensibility Guide
To add a new topic to this pillar:
1. Create a new `### Topic: [Name]` section below with trigger words.
2. Define its scene-by-scene narrative structure.
3. Ensure **Scene 1** adheres to the concise Leading Hook (15–25 words max).
4. Ensure the **Final Scene** delivers the concise Call-To-Action (10–20 words max).

## 📚 Topics

> **Dynamic Layout Selection:** Do not force scenes into a rigid structure. For each scene, actively collaborate with the user or use your best judgment to determine the optimal layout `type` (`description`, `quote`, or `bullet_points`) based on the specific content and flow of the video. Ensure the drafted content naturally fits the chosen type while retaining enough detail for the alternative fields.

### Topic: Product Launch / Promo
**Trigger Words:** promo, commercial, launch, feature announcement
**Narrative Structure:**
1. **Scene 1: The Hook** - Introduce the core problem or make a bold claim.
2. **Scene 2: The Reveal** - Introduce the product/feature as the solution.
3. **Scene 3: The Value Props** - Break down key benefits using the `features` array.
4. **Scene 4: The CTA** - Call to action (e.g., "Try it free today").

### Topic: Sales Proposal
**Trigger Words:** proposal, contract pitch, SOW
**Narrative Structure:**
1. **Scene 1: The Objective** - State the client's main goal.
2. **Scene 2: The Scope** - High-level deliverables.
3. **Scene 3: The Investment** - Timeline and pricing.
4. **Scene 4: The Next Step** - Call to action to sign/approve.

### Topic: Investor Pitch
**Trigger Words:** investor pitch, fundraising, deck
**Narrative Structure:**
1. **Scene 1: The Problem & Market** - The big problem you are solving.
2. **Scene 2: Traction** - Revenue, active users, growth metrics.
3. **Scene 3: The Team** - Why you are the right people.
4. **Scene 4: The Ask** - How much you are raising.

## 🛑 MANDATORY SCHEMA ENFORCEMENT
Once you have finalized the narrative and scene structure based on the chosen topic above, you **MUST** format the final output using the strict rules and schema defined in the `create-video` skill. You cannot output raw text; you must hand off to the `create-video` compiler to generate valid Onvidio JSON.
