---
name: create-video-education
description: Trigger this skill when the user asks to create a tutorial, knowledge video, concept explainer, onboarding guide, or visual FAQ.
---

# Education Pillar Playbook (Instruction & Support)

This pillar handles videos designed to teach the viewer, answer questions, and reduce support tickets. The tone should be clear, methodical, step-by-step, and patient.

## 🎬 Leading & Closure Framing

Every educational video must bookend its narrative with clear learning outcomes:

### 1. The Leading Scene (The Learning Objective / Curious Hook)
* **Concise & Immediate:** Spoken narration must be **strictly 15–25 words max**. Hook the viewer in 3 to 5 seconds by stating what they will master or the curious question.
* **Category Eyebrow:** E.g., `OBJECTIVE`, `WHAT YOU'LL LEARN`, `THE QUESTION`.

### 2. The Closure Scene (Summary & Next Steps)
* **Punchy & Decisive:** Spoken narration must be **strictly 10–20 words max**. Provide a crisp summary or direct the viewer to documentation/support.
* **Category Eyebrow:** E.g., `SUMMARY`, `NEXT STEPS`, `RESOURCES`.

## 🏗️ Extensibility Guide
To add a new topic to this pillar:
1. Create a new `### Topic: [Name]` section below with trigger words.
2. Define its scene-by-scene narrative structure.
3. Ensure **Scene 1** adheres to the concise Learning Objective / Hook (15–25 words max).
4. Ensure the **Final Scene** delivers the concise Summary / Resource wrap (10–20 words max).

## 📚 Topics

> **Dynamic Layout Selection:** Do not force scenes into a rigid structure. For each scene, actively collaborate with the user or use your best judgment to determine the optimal layout `type` (`description`, `quote`, or `bullet_points`) based on the specific content and flow of the video. Ensure the drafted content naturally fits the chosen type while retaining enough detail for the alternative fields.

### Topic: Instructional / How-To
**Trigger Words:** tutorial, how to, step by step, guide, onboarding
**Narrative Structure:**
1. **Scene 1: The Goal** - What the viewer will achieve by the end.
2. **Scene 2: Step 1** - The first action.
3. **Scene 3: Step 2** - The next action.
4. **Scene 4: Summary/Next Steps** - Wrap up or where to get more help.

### Topic: Concept Explainer / Knowledge
**Trigger Words:** explainer, what is, history of, concept
**Narrative Structure:**
1. **Scene 1: The Curious Hook** - Ask the core question (e.g., "Why is the sky blue?").
2. **Scene 2: Background Context** - Provide necessary history or baseline info.
3. **Scene 3: The Core Mechanism** - Break down how it actually works.
4. **Scene 4: The Takeaway** - The final "Aha!" moment or conclusion.

### Topic: Visual FAQ
**Trigger Words:** FAQ, support answer, return policy, help desk
**Narrative Structure:**
1. **Scene 1: The Question** - The exact user question.
2. **Scene 2: The Direct Answer** - A fast, clear answer.
3. **Scene 3: Details** - Any caveats, links, or conditions.

## 🛑 MANDATORY SCHEMA ENFORCEMENT
Once you have finalized the narrative and scene structure based on the chosen topic above, you **MUST** format the final output using the strict rules and schema defined in the `create-video` skill. You cannot output raw text; you must hand off to the `create-video` compiler to generate valid Onvidio JSON.
