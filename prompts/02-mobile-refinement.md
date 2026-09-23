MOBILE EXPERIENCE — REQUIRED

Design mobile as an intentionally composed experience within the same website and codebase. Adapt navigation, typography, spacing, fly-through framing and scroll timing for small screens. Reuse the desktop fly-through footage; do not generate new video for mobile.

1. PERSISTENT MOBILE NAVIGATION

Keep a compact navigation bar fixed to the top of the viewport throughout the entire website, including after the fly-through ends.

Place the brand symbol and wordmark on the left and a hamburger menu on the right. Both must remain visible while scrolling. Keep the wordmark on one line; shorten or scale it rather than letting it wrap.

Mount the navigation outside the pinned fly-through section so it cannot disappear when that section ends. Ensure its stacking order keeps it above the animation and page content.

Respect phone safe-area insets and provide at least 44 × 44 px touch targets.

The hamburger must open an accessible menu with clear navigation links, the primary action, a close button, keyboard support, focus management, and Escape-to-close behavior. Close it after selecting a link. Lock background scrolling while the menu is open.

Offset anchor destinations so the fixed header does not cover section headings (for example `scroll-padding-top` equal to the header height plus a small gap).

2. GLASS-TO-SOLID HEADER

The header has two states, on mobile and desktop alike.

Over the fly-through (glass): the header is see-through, so the footage flows behind it. Use a gradient of the brand's darkest colour, strongest at the very top (about 70% opacity) and fading to fully transparent at the bottom edge, so there is no hard line. The logo, menu icon and primary action must stay legible over the brightest frames. Test against the lightest scenes, not only the opening frame.

After the fly-through (solid): once the pinned section has scrolled past, the header switches to a nearly opaque background in the same dark colour (about 90–95%), with a backdrop blur (`backdrop-filter: blur(10px)` plus the `-webkit-` prefix) and a subtle hairline border, so navigation stays crisp over light sections, cards and forms.

Implementation:
- Decide the state from the fly-through section's position: solid when its bottom edge reaches the header's bottom edge. Recompute on scroll (passive listener), resize and orientation change, and once on load for pages opened mid-scroll or via an anchor.
- Toggle a single state class. Transition only background, border and blur, over about 250–350 ms. Never animate layout, height or position, so the header doesn't jump.
- Revert to glass when scrolling back up into the fly-through.
- The open mobile menu always uses the solid treatment, whatever the scroll position.
- For reduced-motion visitors, switch states instantly.
- If the browser lacks backdrop-filter, the solid state still works because its background is nearly opaque.

3. MOBILE HERO COMPOSITION

Prioritize the fly-through. Keep the opening screen simple:
- Persistent glass navigation.
- One short headline.
- One primary action.
- A subtle scroll cue.

Remove or shorten supporting paragraphs, decorative labels, and secondary actions when they compete with the footage.

On phones, anchor chapter copy to the lower part of the screen over a soft bottom-up scrim, rather than beside the subject as on desktop. Keep it clear of the doorway or path the camera is flying towards and of the fixed navigation.

During the flight, let the footage fill the screen with minimal overlays: one short heading per chapter, with body copy trimmed or hidden. Reintroduce concise copy and an action at the final aerial reveal.

4. REUSE THE WIDESCREEN FLY-THROUGH ON MOBILE

Do not re-animate for mobile. A first-person fly-through keeps its subject (the doorway, aisle or path ahead) near the horizontal centre of the frame, so the same footage reads naturally on a tall screen when centre-cropped.

Render the fly-through into a full-screen canvas using a cover fit: scale each frame to fill the viewport height and crop the sides evenly (the canvas equivalent of `object-fit: cover`):

```text
scale = max(canvasWidth / frameWidth, canvasHeight / frameHeight)
drawWidth = frameWidth * scale, drawHeight = frameHeight * scale
x = (canvasWidth - drawWidth) / 2, y = (canvasHeight - drawHeight) / 2
```

Size the canvas backing store to the viewport multiplied by device pixel ratio (capped at 2) and recompute on resize and orientation change.

Before relying on the crop, check the centre ~45% of the frame (the portion a 9:16 phone shows from 16:9 footage) through the whole flight:
- Doorways, turns and the path ahead stay inside the crop.
- People and key objects (a staff member opening a door, a technician, a hero product) are not cut in half at the key moment.
- The 180° spin and the final aerial still read. The whole building should be recognisable in the centre crop of the final frames.

If a moment falls outside the centre, shift the crop for that beat only: store an optional horizontal focus per beat (0 = left edge, 0.5 = centre, 1 = right edge) in the content file and ease between focus values across beats instead of jumping. Only if the crop cannot be rescued, note it; do not silently generate new footage.

Optional bandwidth optimisation: from the same master video, extract a dedicated portrait-cropped sequence for phones (for example FFmpeg `crop=ih*9/16:ih` with the same per-beat focus, at the source's native resolution; never upscale), and have phones request only that sequence. It is the same footage, just pre-cropped, so it looks identical and downloads less.

5. MOBILE SCROLL PACING

Tune mobile scroll timing independently from desktop. The beat timeline lives in the content file; allow a mobile override of each beat's scroll distance.

Keep the flight moving with normal thumb gestures. Shorten still-frame holds, and give dense interior manoeuvres enough distance to read as motion. Give the 180° spin its own short beat so it doesn't feel like a jump. Adjust the scroll-to-frame mapping rather than removing frames; removing frames alone does not shorten the scroll distance.

Use brief opening and closing holds so visitors can read the headline and take in the final aerial.

Keep a visible "Skip the tour" link to jump past the flight to the main content.

6. ASSET DELIVERY AND PERFORMANCE

Show a lightweight poster (the first frame) immediately. Load frames progressively around the current scroll position, prioritizing the frame the visitor needs now and prefetching in the scroll direction.

Limit simultaneous requests and decoded-image memory, abort obsolete requests on fast scrolls, and release evicted bitmaps. Cache-bust frame URLs with a version from the manifest so replaced sequences never show stale frames.

If you add the optional portrait-cropped sequence, select the right sequence before requesting any frames: phones request only portrait frames, desktops only landscape. Do not preload both and hide one with CSS. When the viewport crosses the breakpoint, cancel obsolete requests and release decoded images from the previous sequence.

Use responsive image sizes for other large imagery (stock photos, lifestyle bands) as well.

Do not block the page until the whole sequence downloads. Keep the rest of the site usable while media loads.

Respect reduced-motion preferences by showing composed stills and normal page flow without fetching the sequence. Provide a usable poster fallback if loading fails.

7. MOBILE LAYOUT FOR THE REST OF THE SITE

Reflow every section for a single column rather than shrinking the desktop layout:
- Search and filter bars stack their fields full-width, with a full-width primary button.
- Category tabs wrap or scroll horizontally without overflowing the page.
- Card grids go to one column (or two only where cards stay legible).
- Step sequences stack vertically; drop connector lines that no longer connect.
- Calculators, sliders and forms use full-width controls with touch-sized targets.
- Image bands move their text to the bottom over a bottom-up scrim.
- Footer columns collapse to two columns or a single column.

8. MOBILE VALIDATION

Preview the actual implementation at several phone widths and heights (for example 360 × 740, 375 × 812, 390 × 844, 430 × 932), in portrait and landscape.

Inspect:
- Opening composition and immediate readability.
- The centre crop keeping doorways, turns, people and the path ahead in frame through the whole flight.
- The spin and final aerial still reading in the crop.
- Scroll pacing through the interior, the exit, the spin and the reveal.
- Text and buttons staying clear of the subject.
- Glass header legibility over the brightest frames, and the switch to solid exactly when the fly-through ends, in both scroll directions.
- Persistent navigation after the fly-through ends.
- Menu opening, closing, focus behavior, scroll lock and anchor offsets.
- Safe-area spacing and absence of horizontal overflow on every section.
- Reduced-motion and loading-failure behavior.

Check desktop again after mobile changes, including both header states.

When network inspection is available, verify which frame assets each viewport requests. Report measured asset sizes separately from actual loading-speed measurements; do not promise speed based on file size alone.

Leave a mobile preview available for review and explain that mobile and desktop are responsive versions of the same website, sharing the same fly-through footage framed for each screen.
