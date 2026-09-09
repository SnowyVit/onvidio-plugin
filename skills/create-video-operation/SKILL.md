---
name: create-video-operation
description: Trigger this skill when the user asks to create an internal team update, job ad, async standup, or company announcement.
---

# Operation Pillar Playbook (Internal & HR)

This pillar handles videos designed to keep the team aligned, hire talent, and replace unnecessary meetings. The tone should be professional, concise, and culture-driven.

## 🏗️ Extensibility Guide
To add a new topic to this pillar, simply create a new `### Topic: [Name]` section below and define its scene-by-scene narrative structure.

## 📚 Topics

> **Dynamic Layout Selection:** Do not force scenes into a rigid structure. For each scene, actively collaborate with the user or use your best judgment to determine the optimal layout `type` (`description`, `quote`, or `bullet_points`) based on the specific content and flow of the video. Ensure the drafted content naturally fits the chosen type while retaining enough detail for the alternative fields.

### Topic: Recruitment / Job Ads
**Trigger Words:** job ad, hiring, open role, careers
**Narrative Structure:**
1. **Scene 1: The Hook & The Role** - State the open role and mission.
2. **Scene 2: The Challenge** - What the candidate will actually be doing.
3. **Scene 3: The Requirements** - Must-have skills.
4. **Scene 4: The Offer & Culture** - Salary, benefits, perks.
5. **Scene 5: The CTA** - Where to apply.

### Topic: Async Standup / Team Update
**Trigger Words:** standup, weekly sync, team update, changelog
**Narrative Structure:**
1. **Scene 1: The Highlight** - The biggest win or goal for the week.
2. **Scene 2: Key Metrics/Progress** - What got done.
3. **Scene 3: Blockers** - What is standing in the way.
4. **Scene 4: Next Steps** - Focus for next week.

### Topic: Townhall Recap
**Trigger Words:** townhall, all hands, company meeting
**Narrative Structure:**
1. **Scene 1: The Theme** - Overall sentiment of the meeting.
2. **Scene 2: Major Announcements** - Key takeaways.
3. **Scene 3: Shoutouts** - Recognizing team members.

## 🛑 MANDATORY SCHEMA ENFORCEMENT
Once you have finalized the narrative and scene structure based on the chosen topic above, you **MUST** format the final output using the strict rules and schema defined in the `create-video` skill. You cannot output raw text; you must hand off to the `create-video` compiler to generate valid Onvidio JSON.
