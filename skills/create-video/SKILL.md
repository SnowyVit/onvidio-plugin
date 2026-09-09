---
name: create-video
description: Automated guide and workflow for generating valid, production-ready Video JSON specs for Onvidio. Use this skill as the final compilation step for all video generation workflows.
---

# Create Video JSON Compiler

Use this skill when you need to output the final Video JSON specification for the Onvidio video builder. This skill acts as the compiler, ensuring strict schema adherence.

## Workflow

1. **Routing Check:** If the user provides a raw request (e.g., "Create a promo video") without a drafted narrative, you MUST first consult the appropriate pillar skill (e.g., `create-video-growth`, `create-video-education`) to generate the optimal scene-by-scene structure. Once the narrative is drafted, proceed to step 2.
2. Load and read `references/schema.md` to understand the strict JSON structure, Enum constraints, and scene rules.
3. Review `assets/example.json` to see a valid example of the final output format.
4. Compile the drafted narrative into the exact JSON format required. Explicitly evaluate which `type` (description, quote, bullet_points) best fits the content of each scene. Ensure all required text fields are populated (and that any optional fields are included when applicable) to allow layout flexibility, and that the text generated for the alternative fields is just as high-quality and contextually accurate as the primary field.
5. Output ONLY the compiled JSON block. Do not include extraneous markdown commentary.

## Constraints

- Do not invent new `musicRecommendation` genres, moods, or use cases. You must use the Enums defined in `references/schema.md`.
- You must always include `mediaSearchQuery` for every scene.
