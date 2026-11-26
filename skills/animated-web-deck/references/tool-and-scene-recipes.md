# Tool and scene recipes

## Audit a reference deck

1. Start from the loaded `script`, `link`, media and module references. Read the source paths that actually generate the visible effect. A screenshot can identify a visual style, but layered CSS, SVG, WebGL, or a pre-rendered video can look similar.
2. Inventory assets by type and purpose. Check for one-frame versus animated images, font weights, poster images, and looping videos. Read authoring metadata when present. Use a few video frames to see whether motion comes from framing, moving objects, or compositing.
3. List each finding with evidence and confidence. `element.animate()` and a CSS animation in source establish runtime technology. A `Lavf` or `Lavc` tag points to FFmpeg libraries somewhere in media preparation. It does not identify a specific editor, generator, or CLI workflow. An anonymous image and a thin deployment manifest leave their authoring tools open.
4. If the user asks for tools, provide source links plus a shortlist of plausible recreation tools by job. Install or use the tools actually needed by the requested deliverable.

Example inspection command. Quote paths with spaces.

```sh
ffprobe -v error -show_entries stream=codec_name,width,height,r_frame_rate:stream_tags=encoder:format=duration:format_tags=encoder -of json "background.mp4"
```

## Apply a design reference

1. If the user supplies a link, open the exact page or anchored section. For a live reference, inspect representative screens and any relevant interactions at the size the user will present. If motion matters, observe what changes while idle and what changes after an action. Record only what you can see. For a blocked link, ask for a screenshot, short recording, or direct link to the relevant section. Continue the content outline while waiting. If the user delegates or leaves the choice open, use a stated provisional direction.
2. If the user wants suggestions, show two or three distinctive options suitable for the audience and material. When offering links, open them first and name the concrete feature each demonstrates. For example, point out a restrained title and image spread, a legible sequence of task screens, or a diagram with motion on the active path. Offer a one-line choice in the user's language, such as “참고 링크나 캡처가 있으면 보내주세요. 아래 방향 중 하나를 골라도 되고, 교안에 맞춰 제가 정해도 됩니다.”
3. Translate the chosen reference into a short set of decisions. Look at the title and body type hierarchy, palette and contrast, grid and spacing, image treatment, presenter navigation, and motion. Carry over only the relevant patterns. With multiple links, use the user's stated roles, such as one for the cover and one for motion. Ask which to prioritize only if their directions conflict and the choice would change the result.
4. Apply the decisions to a cover and a representative content slide before extending them across the deck. Adapt the composition to the lesson, projection distance, Korean text, and presentation controls. Create original visuals or use assets the user can reuse. When the user asks to match a reference they own or are authorized to reproduce, follow the requested level of fidelity. Otherwise adapt the patterns with the new deck's own composition and assets.
5. Compare the rendered sample slides with the decisions you recorded. Check that the selected layout, typography, visual treatment, and requested motion appear on screen and remain readable at the intended size. If a reference detail had to change for the teaching context, name the change briefly in the handoff.

When a source is supplied for lesson content, use it to ground the teaching material. Apply its visual style if the user also chooses it as a design reference.

For example, a link chosen for its cover might lead to a left-aligned title with an original illustration on the right, while a second link chosen for motion might lead to a slow loop confined to the illustration. Apply both decisions to an actual slide before repeating them across the deck.

## Choose the smallest stack

| Need | Tool or technique | Where to read |
|---|---|---|
| Author and present a portable web deck | HTML, CSS, vanilla JS, separate slide data and local fonts | [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) |
| Ambient parallax, drifting props, ticker or path markers | CSS keyframes using transform/opacity, plus reduced-motion rules | [CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations), [Reduced motion](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@media/prefers-reduced-motion) |
| Sequenced entrance, step reveal or coordinated elements | Web Animations API for simple groups. Anime.js for timelines or repeated orchestration | [WAAPI](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API), [Anime.js](https://github.com/juliangarnier/anime) |
| Draw precisely along a path or move part of an image | SVG path length, clip paths or masks. Use a scene-owned animation frame only for behavior that needs it | [SVG geometry](https://developer.mozilla.org/en-US/docs/Web/API/SVGGeometryElement/getPointAtLength) |
| Original illustration or separated paper/clay props | An available image-generation tool, or suitable user-supplied or licensed illustrations. ComfyUI when local node-based generation is appropriate and available | [ComfyUI](https://github.com/Comfy-Org/ComfyUI) |
| Reuse an existing animation or add real spatial manipulation | Lottie for an existing Lottie export. Three.js when the scene needs camera or 3D interaction | [Lottie Web](https://github.com/airbnb/lottie-web), [Three.js](https://github.com/mrdoob/three.js) |
| Video-only scene, optional intro loop, or requested video export | Remotion for composed frame-based video. FFmpeg for media preparation, posters and final encoding | [Remotion](https://github.com/remotion-dev/remotion), [FFmpeg](https://github.com/FFmpeg/FFmpeg) |

Inspect primary documentation and license terms for packages, models, fonts and assets before using them. Pin dependencies and store fonts, licenses and optimized images with a portable deck. The broader `motion-graphics-toolkit` inventory covers other specialized media tools.

## Plan scene variety

| Example beat | Composition | Idle motion | Presenter action |
|---|---|---|---|
| Opening | Large live heading with calm negative space opposite a full-width custom illustration | Slow parallax and a few floating props | Advance to agenda |
| Name a problem | Asymmetric illustration and short numbered rows | A slight pan that leaves the prompt legible | Reveal constraints one at a time |
| Explain a data flow | SVG or HTML diagram with direction and state labels | Particles traverse only the routes already shown | Reveal blocked access, authorization and response in order |
| Work through a procedure | One realistic, interactive UI specimen | Optional subtle signal near the relevant control | Click, try, compare and check |
| Pause or transition | Full-scene illustration, big title, visible time or destination | Slow motion and no flashing | Continue when ready |

Build for the delivery canvas and the viewing distance. Keep essential copy inside a safe area and use the decorative image layer for bleed. Prefer a new illustration when a new concept needs a new subject. Recurring chapter motifs can reuse imagery intentionally.

## Topic navigation and visual hierarchy

The [summer safety training deck](https://summersafety2026.vercel.app/) pairs a clickable topic map with a repeatable text-and-illustration layout and a quick-reference slide. Adapt these patterns to the presentation:

- Give each topic a short label and a recognizable icon. Link it to the first slide of that topic. Keep the topic map, previous/next controls, and current slide number within easy reach. Add fullscreen when it helps the presenter.
- For related procedure slides, keep the action-oriented heading and short numbered instructions on one side and a relevant illustration on the other. Give each row a clear action and a brief explanation. Carry the topic name alongside any topic-specific color. Stack the columns on narrow screens and let the content take the height it needs.
- Give information the audience may need to retrieve quickly its own slide. Pair each prominent value or shortcut with a plain-language purpose. Use the recap to bring back the main actions in presentation order when that order matters.
- When supporting both scrolling and presenter controls, keep navigation and the slide counter tied to the same active slide. Use scroll snap only where slides fit the viewport comfortably. In short or narrow viewports, let the content scroll naturally and reserve room for fixed controls so the last topic card and final instruction stay visible and reachable.

## Keep loops separate from progression

For CSS loops, give the animated descendants an explicit class. Use a parent state to pause the loops and the system preference to remove them. With CSS motion disabled, supply a readable rest pose.

```css
[data-motion-paused="true"] .ambient {
  animation-play-state: paused;
}
[data-motion-enabled="false"] .ambient {
  animation: none;
}
@media (prefers-reduced-motion: reduce) {
  .ambient { animation: none; }
}
```

Keep entry animations separate from these selectors. If the instructor switches motion off mid-entry, finish or set the visible end state before canceling. For WAAPI, SVG loops or video, maintain one cleanup function per scene. On slide navigation, stop the old scene before mounting or starting the next. Don't keep a hidden loop alive to implement a transition.

For a true video background, use muted inline playback with a local poster. Keep the poster visible when autoplay is denied or motion is disabled. Use a plain figure and CSS pan when that achieves the requested effect with fewer assets.

## Verify the delivered behavior

- With the slide and reveal state fixed, observe the image crop, transform or packet position at two distinct times. Confirm the visual changes and the presentation state does not.
- Pause through the presentation control and test system reduced motion. Open and close any presenter panels and test leaving and re-entering a moving slide.
- Inspect the final reveal on every slide for clipping. Check Korean word breaks, the cover title against the artwork, background control contrast, and a tall portrait viewport if supported.
- Follow the key interactions using the real entry point. Try previous/next, a direct slide jump, a form field without accidental navigation, and any task-specific demonstration. Confirm that locally bundled images, fonts and scripts load without remote requests when offline use was requested.
