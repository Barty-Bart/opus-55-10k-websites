# Build a cinematic drone fly-through website

Act as a designer, creative director and website developer. Build the actual website, including its visual assets and working scroll animation. The centrepiece is **one continuous first-person fly-through** of the business: a single unbroken camera move that enters the building, travels through its spaces the way a real FPV pilot would fly them, exits, and reveals the whole place from the air. Motion, typography and content should feel composed together.

Use Higgsfield MCP for generated images and video. Stay in the current conversation and project. Do not silently substitute browser control, another generation provider, or another conversation. A skill supplies instructions, not tool access: verify the required image/video tools are callable before promising generation. If they are missing, state the exact capability gap once, ask for the smallest necessary action, and continue independent work. Do not repeatedly recommend reinstalling an already connected plugin.

## 1. Establish the brief with minimal friction

Read the conversation and supplied materials first. Ask only questions whose answers materially affect the result. When information is missing, a single compact intake can cover:

- What does the business do, who is it for, and what should visitors do on the site?
- Is there a business name, logo or existing brand identity to use?
- Are there websites or visual references to follow, or a description of the desired aesthetic?
- What is the physical route? Which spaces should the camera pass through (for example entrance, showroom, workshop, storage, rear yard), and where should it exit?

Do not repeat answered questions or require a full branding questionnaire. A business description is enough to begin; if the route is not given, propose a realistic one for that type of premises.

Recognize two modes:

**Guided mode:** Use a small number of meaningful review points: identity/style direction, the start still, and the proposed flight path. Show concrete options rather than asking abstract questions repeatedly. Once a direction is chosen, move forward.

**Template or autonomous mode:** If the user says “build a template,” “choose for me,” “assume the answers,” or similar, choose suitable defaults and complete the build without waiting for aesthetic decisions. Missing copy is not a blocker. Use a coherent content scaffold, keep it easy to replace, and record assumptions in the handoff. The user can supply final business details later.

Preserve real supplied facts. Do not fabricate testimonials, customers, awards, addresses, experience, project counts or other credibility claims. For a fictional or template business, make the demo status clear and use useful placeholders where real details are required.

## 2. Establish an identity and a real design board

If a logo or official assets are supplied, preserve them. Distinguish inspiration from material the user owns or has declared authoritative. Do not redraw an existing logo to make it fit a new aesthetic.

If identity is missing, develop a small set of appropriate directions. Use Higgsfield MCP to generate logo concepts when a logo is needed. Select the strongest in autonomous mode; otherwise show a compact selection. Prefer an editable vector master when the available model supports it. A raster export is not an SVG master.

Inspect supplied reference websites before describing their design. Extract useful characteristics such as typography, spacing, contrast, composition, materials, component treatment and motion. Do not copy proprietary branding or distinctive artwork wholesale.

Without references, infer a coherent direction from the business and the user's description. Avoid defaulting every business to the same template.

Create a compact **style tile** using the actual website design tokens. Include the chosen logo, colour palette, heading/body typography, buttons, links, a sample card or service component, and imagery direction. Prefer an editable HTML/CSS board that can be viewed alongside the site. This is a design sample, not a screenshot of a finished website and not a full brandbook.

Maintain one consistent identity across the board, generated assets, and website. Keep the selected source assets, prompts and selection rationale.

## 3. Design the flight path

Translate the business's premises into one continuous flight. The camera never cuts and never teleports between rooms: every change of space happens by physically flying through a doorway, round a corner or out of an opening. The story is the route.

**Present the flight before production.** Start with a concise table titled **Visual Story**, using exactly these three columns: **Scene**, **Visual story**, and **Website copy**. Each row is a stretch of the route and pairs what the camera does with draft headings, supporting copy and relevant calls to action. Write business-specific proposals rather than empty placeholders.

Use this table structure, replacing the descriptions with the actual proposed route:

| Scene | Visual story | Website copy |
| --- | --- | --- |
| 01 — Arrive | Exterior approach at eye height; arc past a key object and line up with the open entrance, then glide in. | Draft hero heading, supporting line and primary action. |
| 02 — Main space | Slow down, sweep along the side of the hero product, S-curve around a second one, yaw to look across the room. | Draft offering heading, supporting copy and action. |
| Transition — Doorway | A staff member opens a door and the camera flies straight through. | No copy — let the motion lead. |
| 03 — Back-of-house | Arc around the work being done, dip to look closer, curve past equipment. | Draft service/craft heading and action. |
| 04 — Storage / route out | Turn through a side door, weave an aisle, turn at the end, round a corner to the exit opening. | Draft supporting heading. |
| Transition — Exit and turn | Fly out through the rear opening, keep moving, then yaw 180° to face the building just exited. | No copy — let the motion lead. |
| 05 — Reveal | Fly backwards and climb, revealing the whole premises connected to its roads and surroundings. | Draft closing heading, business information and closing action. |

Add or remove rows to fit the premises. After the table, briefly explain the route and how scrolling introduces, holds and removes the website copy.

### Fly it like a real pilot

A fly-through that glides down a straight rail reads as a camera dolly, not a drone. Write the route with the manoeuvres a pilot would use:

- **Vary speed.** Slow down for detail, speed up through transitional space.
- **Bank and drift sideways.** Arc past objects so their side profile is seen, then curve back.
- **Yaw to look around.** Turn the view towards what matters (a product, a technician, a view through windows) while still travelling.
- **Use S-curves** through open spaces and round obstacles.
- **Respect the building.** Interiors are not one straight corridor. Plan realistic turns: through a side door, right at the end of racking, left round a corner to reach an exit.
- **Time each manoeuvre** in the prompt with approximate second ranges (“3–7s: slows, banks left and yaws right along the full side of…”).

### Make the exit and reveal physically correct

- When the camera flies out of a rear opening, the view through that opening must show what is actually outside it (a yard, a service road, a fence, sky), not the front of the building it is inside.
- To reveal the building just exited, the camera **yaws 180° while still moving** so it faces back at the opening, then **flies backwards and climbs**. Do not fly forward out of a building and see that same building ahead.
- The final aerial must place the premises realistically: an access road, car park or forecourt, the main road it faces with traffic, and neighbouring buildings or landmarks. Never leave it floating in an empty field.
- Keep the building's architecture consistent with the start still: same materials, frames, glazing and scale.

### Scroll pacing

Beneath the table, give a concise **Scroll pacing** plan for each scene and transition: what enters/exits view, approximate active scroll distance in viewport heights, and whether the beat uses continuous motion or a still-frame hold. Hold the opening frame long enough for the hero copy to be read, give the dense interior manoeuvres more scroll distance, give a fast yaw or spin its own short beat so it doesn't feel like a jump, and hold the final aerial at the end.

Assign scroll distance independently of clip duration and frame count. Measure pacing in viewport heights, not mouse-wheel turns. Use a piecewise scroll timeline: each beat maps its own scroll interval to its own frame interval, and a hold maps an interval to a single frame. Count active pinned scroll travel separately from the height of the visible stage.

Where browser interaction checks are permitted, validate the actual experience with ordinary scrolling and adjust. If interaction testing is unavailable, disclose that pacing remains unverified rather than claiming a smooth result from compilation alone.

In guided mode, present the table and route explanation for feedback before generating footage. In autonomous/template mode, still present them, then continue without waiting.

Plan responsive composition now. Reserve space for text and avoid important action on both extreme edges.

## 4. Generate the flight as one chained take

Check the live model schema before submitting: duration limits, aspect ratio, resolution, reference roles and the available modes. Use the user's requested provider and preserve their billing preferences. Creating the requested assets does not authorize buying a subscription or changing account settings.

### Stills first

1. Generate 2–3 **start stills** in different directions: an eye-level exterior view of the entrance with the doors open, inviting the camera in. Choose one (or let the user choose). This becomes the exact first frame.
2. Generate a **reveal reference still** from the chosen start still: a high aerial looking back at the rear of the same building, showing the exit opening, the yard, the full premises and its connected roads. This is the target for the final shot and keeps the architecture consistent.

Avoid real brand names, logos and distinctive trade dress in prompts (for example real car marques); request unbadged products and no signage lettering.

### Chain the clips with extension, not separate scenes

Split the route into 2–3 segments of up to about 15 seconds each so every manoeuvre gets enough time. Generate them as **one continuous take**:

- **Clip A:** image-to-video (for example Seedance 2.5 `omni_reference`) with the start still as `start_image`, covering the entrance and main space.
- **Clip B:** the model's **video extension** mode (for example Seedance 2.5 `video_extension`, `extension_mode: forward`) with clip A as the reference video, continuing through back-of-house and storage.
- **Clip C:** extension of clip B, plus the reveal reference still as an image reference, covering the exit, the 180° yaw and the reverse climb.

Extension continues the same camera, lighting and speed from the previous clip's last frame, which is what makes the flight feel unbroken. Do not generate independent scenes and hope a crossfade hides the change.

Generate the segments in order and inspect each before starting the next. Keep job IDs and retrieve existing results before submitting duplicates. A pending job is not a failed job. Work on the website while clips render.

### Prompt wording that matters

- **Never write the word “drone” (or “quadcopter”, “UAV”) in a video prompt.** Models draw a drone flying through the shot. Describe the camera instead: “one single continuous first-person camera move, no cuts; the camera itself is flying; nothing flying or hovering is ever visible in frame.”
- State “every vehicle/person/object is stationary unless described; nothing appears, disappears or changes” so products don't pop in and out.
- Give each segment timed manoeuvres and say what is visible through the next opening.
- Specify warm/cool lighting, lens look and “no text, no logos, no brand badges, no signage lettering.”
- If the platform suggests a preset that doesn't match the brief, decline it and generate the prompt literally.

### Inspect every clip

Use FFmpeg (for example `npm install -g ffmpeg-static` when Homebrew isn't available) to:

- make a contact sheet at 1–2 frames per second and view it;
- run scene-cut detection (`select='gt(scene,0.3)'`) to confirm there are no hidden cuts;
- zoom into the final seconds and any doorway or turn;
- compare the last frame of each clip with the first frame of the next.

Look for stray drones or objects, cars or people appearing from nowhere, logos, unrealistic geography, and jumps in position, scale or lighting.

### Repair instead of regenerating

A full regeneration of an extension is expensive. Prefer targeted repairs:

- **Trim to clean frames.** If an artefact appears late in a clip, cut the clip before it, upload the trimmed file (`media_upload`, PUT the bytes, `media_confirm`) and extend from the trimmed version.
- **Edit out small artefacts.** For a stray object in a short stretch, cut that stretch out, run a text video-edit (for example FLUX 3 Video Edit: “remove the small flying quadcopter from every frame; keep everything else identical”) and splice it back. Edits may return at a lower resolution; note the softer section. Requests to remove brand logos may be blocked by content filters, so keep edit instructions to the object removal.
- **Extend from a clean tail.** If the start of a clip is repaired but the end is fine, upload the clean tail and extend from it for the next segment.

Do not run an open-ended regeneration loop. Preserve already useful assets.

### Stitch one master

Assemble the segments with FFmpeg into one master:

- normalize every segment to the same size, frame rate and pixel format (`scale=1920:1080:flags=lanczos,fps=24,format=yuv420p,setsar=1`);
- join segments that came straight from an extension with a **hard concat** (they already match);
- where an edited or repaired piece meets an original one, or a clip boundary shows a small jump, use a very short **crossfade** (`xfade=transition=fade:duration=0.125`);
- re-run cut detection on the master and view a contact sheet of the whole flight.

Record actual credit use. Extension jobs can cost more than the cost preflight reports because they also process the input clip; check the balance after each job and budget accordingly.

### Prepare the frame sequence

Extract a browser-ready image sequence into a fresh staging directory:

```sh
ffmpeg -i flythrough-master.mp4 -an -vf "fps=20,scale=1440:-2:flags=lanczos" -c:v libwebp -quality 78 -start_number 0 frames/frame-%04d.webp
```

Use 18–24 fps: higher rates help fast yaws and spins stay smooth when scrubbed. Adapt size and quality to the measured transfer size. Write a manifest with the actual count, fps, dimensions, naming pattern, poster and a version value used to cache-bust frame URLs. Verify the first, middle and last frames and all referenced paths before integration.

## 5. Build a complete, usable website

Reuse the current project and suitable existing components. Follow the hosting environment's required build/deployment workflow, if present.

Build the site's business structure as well as its animation: useful navigation, clear offering, relevant sections and a primary action.

Implement the fly-through with a pinned canvas stage. Map scroll to frames through the piecewise beat timeline, with each beat stored in an editable content file (`vh`, clip `from`/`to` seconds, and which chapter of copy it carries). Copy fades in, holds and fades out within its beats; the first chapter is visible at rest and the last holds at the end.

Keep motion rendering separate from semantic HTML content. Timed text, buttons and navigation must remain crisp, selectable, accessible and editable. Avoid scroll hijacking; native scrolling must work forwards and backwards. Hidden copy must not intercept clicks or stay in the keyboard order. Provide a “skip the tour” link.

Prioritize the requested frame and nearby frames in the scroll direction. Bound concurrent requests and decoded-frame memory, abort obsolete requests, release evicted bitmaps and use bounded retries. Handle fast jumps, reverse scrolling, resize and high-density displays. Show a poster while frames load. Make the header legible over both the dark stage and any light sections after it.

Provide reduced-motion and constrained-device fallbacks that present each chapter over a representative still. Reflow content for mobile; do not merely shrink the desktop composition. Never make understanding the business depend entirely on seeing the animation.

## 6. Make the content easy to replace, validate and deliver

Keep business copy, service details, calls to action, the beat timeline and media references in a clear content file or an appropriate existing CMS.

Forms need a real submission destination or an explicitly labelled demo behaviour. Never show “sent” if nothing was sent.

Run the appropriate code, build and asset checks. Verify the manifest, frame paths and posters. Check the flight at desktop and phone sizes with the tools permitted in the host: every beat reaches its intended frame, chapters appear on their beats, the final hold works and there is no horizontal scroll. Distinguish checks actually performed from those not performed.

Publish only within the user's authorized scope and audience. Do not silently expose a draft publicly. If publishing is unavailable, deliver a runnable local project and state the missing dependency.

Deliver the website/preview, style tile, logo masters, the start and reveal stills, the original clips, the stitched master, editable content and concise editing instructions. Include a short production note with the chosen direction, the route, prompts, job IDs, repairs made, credits used, important measurements and observed limitations. Exclude credentials and temporary signed URLs from reusable packages.

Continue until the requested result is complete or a concrete dependency prevents it. Show meaningful progress and finished outputs rather than repeated plans.
