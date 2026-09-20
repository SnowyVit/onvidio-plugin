## 1. Core Schema Constraints

When generating a Video JSON spec, the overall object shape must strictly adhere to the `VideoSpec` type defined in `src/components/VideoBuilder/types.ts`. Note that `types.ts` defines the basic structural shape, but strict allowed values (like Enums) and limits are enforced by the backend validators and tool schemas.

### Root Level Requirements
- `type`: Must be strictly `"video"`.
- `title`: A short, descriptive string for the entire video project.
- `scenes`: An array of `VideoScene` objects (max 15 scenes).
- `musicRecommendation`: An object defining the musical vibe for the video.

## 2. Soundtrack & Music Recommendation

Do **not** hardcode a specific `soundtrack.id` unless explicitly instructed by the user, as the user likely does not know internal database IDs. Instead, you MUST provide a `musicRecommendation` block at the root level of the JSON. 

The frontend uses this to score the catalog and auto-select the best matching track.

**Allowed Genres:** `Acoustic`, `Ambient`, `Chillout`, `Cinematic`, `Classical`, `Corporate`, `Electronic`, `Folk`, `Lo-Fi`, `Piano`, `Pop`, `Synthwave`, `Tech`, `Upbeat`, `Vlog`
**Allowed Moods:** `Bright`, `Calm`, `Cheerful`, `Clean`, `Dramatic`, `Dreamy`, `Emotional`, `Empowering`, `Energetic`, `Epic`, `Fast`, `Focused`, `Friendly`, `Gentle`, `Groovy`, `Happy`, `Hopeful`, `Inspirational`, `Inspiring`, `Lively`, `Minimal`, `Modern`, `Motivating`, `Nostalgic`, `Peaceful`, `Playful`, `Positive`, `Relaxed`, `Relaxing`, `Smooth`, `Thoughtful`, `Uplifting`, `Warm`
**Allowed Use Cases:** `Product Promo`, `Tutorial`, `Vlog`, `Background`, `Trailer`, `Social Media`, `Podcast`, `Gaming`, `Presentation`

## 3. Scene Construction Rules

Each scene in the `scenes` array MUST follow these strict guidelines to ensure maximum flexibility in the Onvidio Editor:

### A. Mandatory Scene Core Fields
Every single scene MUST contain the following strictly required fields to satisfy the schema:
- **`id`**: A unique string identifier for the scene (e.g., `"scene-1"`).
- **`mediaSearchQuery`**: A 2-4 word string (nouns/adjectives) describing the visual context. 
  - **CRITICAL RULE**: You MUST include `mediaSearchQuery` even if `imageUrl` or `videoUrl` are already provided. The URLs are only used for initial display; the query is required in case the user wants to search for different stock assets later.

### B. Text Content Hierarchy & Mutually Exclusive Population
To ensure videos look polished across all layout styles, you must strictly follow this semantic hierarchy for every scene's text fields:
- **`category`** (Eyebrow): A 2-4 word catchy summary or theme for the scene (e.g., "The Cold Truth").
- **`title`**: A short, punchy sentence capturing the main point of the scene (e.g., "Distribution is the real bottleneck.").
- **`subtitle`**: A complete, standalone paragraph explaining that main point in conversational detail.
- **`features`**: The exact same main point broken down into a concrete list of 2 to 4 short bullet items.
- **`quote`** & **`author`**: Populate these if the scene's narrative naturally fits as a quote (e.g., a testimonial or key statement). When doing so, set the scene's recommended `type` to `"quote"`.

*Crucial Note*: The Onvidio UI renders only ONE content container at a time based on the scene's `type` (e.g. `description`, `bullet_points`, `quote`). However, you MUST populate all of the core fields (`category`, `title`, `subtitle`, `features`) for EVERY scene to allow users to switch layout styles seamlessly in the editor. `quote` and `author` are only required if the scene is intended to be a quote.

### C. Voiceover / Narration
- **`narration`**: Provide a spoken voiceover script for the scene. This copy must be written for the EAR (natural, conversational) and align with the facts presented on screen.

### D. Recommended Scene Layout
- **`type`**: Set the recommended default layout for the scene. Must be one of: `"description"`, `"quote"`, or `"bullet_points"`.

### E. Optimal Scene Type & High-Quality Alternatives
- **Type Selection**: You must choose the `type` that best represents the primary communication goal of the scene (e.g., select `bullet_points` for a list of benefits, `quote` for a testimonial or bold claim, and `description` for standard narrative).
- **Alternative Field Quality**: Even though you select a primary `type`, you MUST NOT provide lazy or generic text for the alternative fields. Every field (`subtitle`, `features`, `quote`) must be filled with high-quality, perfectly matching content that conveys the exact same message but formatted for that specific field. For example, if the primary `type` is `description`, the `features` array must still contain a meticulously summarized, punchy bulleted version of that exact description.

### F. Universal Bookending: Opening & Closing Scene Requirements
Every compiled video MUST have clearly defined, purposeful opening (Scene 1) and closing (Scene N) scenes. These scenes MUST be **concise, punchy, and clear**:
- **Scene 1 (Opening / Hook):**
  - Narration must be **15–25 words max**. Hook the viewer within the first 3–5 seconds.
  - State the core thesis or headline immediately. No filler greetings or slow build-up.
  - Category and title must clearly anchor the primary subject.
- **Scene N (Closing / Wrap):**
  - Narration must be **10–20 words max**.
  - Deliver a crisp, decisive finish matching the topic (e.g. news kicker/milestone watch, conversion CTA, knowledge recap, or action deadline).
  - Never allow a video to end abruptly without a definitive closure scene.

