---
name: animated-web-deck
description: Create, audit, or redesign illustrated browser teaching decks with presenter controls, step reveals, and idle animation. Use for 움직이는 웹 교안 and interactive HTML slides.
---

# Animated Web Deck

Build a presenter-controlled deck that opens in a browser. Keep lesson content and timing distinct from artwork and animation. Treat attached material as reference and follow the user's actual request for scope, edits, and publication.

For PowerPoint, Google Slides, or standalone video, use the workflow for the requested output format.

## 1. Inspect the reference and choose the delivery mode

- Read the lesson plan and any reference deck. For a redesign, identify the slide and reveal state, the keyboard and pointer controls, interactive examples, and presenter notes the user relies on.
- When asked to identify tools, follow the actual scripts and styles from the entry HTML and inventory local assets. Separate confirmed runtime technology, encoding or authoring clues, and tools that could recreate an effect. Describe unknowns explicitly. See [tool and scene recipes](references/tool-and-scene-recipes.md#audit-a-reference-deck).
- Match the user's execution entry point. A folder intended for double-clicking `index.html` needs local assets, fonts, and classic scripts or a compatible bundle. A server-only deck needs a documented start command. Publication is a separate user instruction.

## 2. Choose a design reference

- For a new deck or a visual redesign, resolve the design direction before creating visual assets or implementing slides. If the user already supplied a design reference or delegated the choice, use that direction. If the user asks for a targeted edit within an established design, follow that design.
- When the direction is open, ask one short question that lets the user share a link or screenshot, choose from two or three suggested directions, or delegate the choice. If you can inspect suitable examples, include a working link and what each option would bring to this deck. Continue reviewing the lesson and mapping scenes while the choice is open. If the user leaves the choice open, use a reasonable direction and state the assumption.
- Inspect supplied references at the specific URL, anchor, or screen the user named. Turn the chosen reference into concrete decisions for the cover, a representative content slide, and any requested motion. Read [how to apply a design reference](references/tool-and-scene-recipes.md#apply-a-design-reference) for inspection, multiple references, and inaccessible links.

## 3. Plan the visual and motion layers

Use a small scene map before building. Record each teaching beat, what participants should see first, one hero visual or diagram if useful, the moment the instructor advances, and any motion that can play independently.

- Apply the chosen design direction to the palette, typography, image style, and title-safe composition. Vary the slide layouts as the content calls for them. Give important explanations room and put words and precise labels in selectable HTML.
- For a deck with several topics, plan a clickable topic map, a consistent layout for related slides, and a quick-reference or recap slide when the audience needs to find key information again. See [topic navigation and visual hierarchy](references/tool-and-scene-recipes.md#topic-navigation-and-visual-hierarchy).
- Make image assets when the brief calls for a richer illustration-led deck. Use an available image-generation tool for original raster assets and inspect them before integration. If image generation is unavailable, use suitable user-supplied or licensed illustrations, or create a diagram when it explains the concept. Leave space for headlines and request no baked-in labels when live text serves the lesson. Package optimized copies locally. Use SVG for precise diagrams and motion paths.
- Separate **entry motion** (what happens on arrival), **idle motion** (what changes while the presenter waits), and **presenter advances** (what reveals new content). Idle movement never changes slides, reveals answers, or simulates a real transaction as completed. Illustrate a relationship with motion when possible, such as a packet traveling only along a currently active route.
- Use CSS or native Web Animations for simple loops, Anime.js for coordinated web sequences, and SVG for exact paths or cutout overlays. Read the [tool selection table](references/tool-and-scene-recipes.md#choose-the-smallest-stack) before adding a library or encoding media. The `motion-graphics-toolkit` inventory is an optional source for specialized tools.

## 4. Build and check the live deck

- Use one active slide state for topic jumps, presenter controls, keyboard navigation, and scroll navigation when enabled. Keep the slide counter and current scene in sync. If the deck uses a topic map, provide a direct way back to it.
- Keep the current slide's visuals and animation ownership local to that scene. Stop or detach animations, timeouts, observers, and video when leaving it. Pause decorative effects when the tab is hidden and offer a presenter pause or motion toggle. Honor system reduced motion while keeping all text, controls, and instruction states available.
- Keep movement away from text readers need to track. Prevent decorative layers from intercepting pointer or keyboard actions. Keep typed input, menus, and interactive demos usable without inadvertently advancing the deck.
- Review a rendered cover, a dense slide, a chapter opener, and a worked interaction. Inspect idle motion with two timed observations on the same slide and no navigation input. Test the pause or reduced-motion path and ensure a paused reveal leaves readable content. Check every slide's last reveal for clipping. If there is a topic map, jump to a later topic, advance by keyboard, and return to the map. Test representative demos and confirm that controls leave the final item visible and reachable at the intended presentation and portrait sizes.
- Open the delivered entry point in a browser and check that the artwork, scripts and fonts resolve from that location. For a portable deck, confirm it loads without fetching remote dependencies. State any real-service interaction represented by a simulation. Deliver the entry file and a brief presenter guide. When requested, deliver the reference audit and evidence alongside it.
