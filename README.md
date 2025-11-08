# Character Counter & Readability Playground

Writing experiment and dumps for testing ideas fast.

Single-file React experience for quickly gauging tweet-length copy and how approachable it feels to different readers. Everything lives in `index.html`, so you can drop it onto any static host (or just double-click it) and start writing.

## Highlights
- 🎯 **Live character & word counts** with limit alerts that flip style once you exceed your cap (default 280, editable in-app).
- 💾 **Persistent state** powered by `localStorage`, so both your text and custom limit survive refreshes.
- 🧠 **Readability coach** calculates a Flesch Reading-Ease score (kid friendly → expert) and summarizes the ideal audience.
- ♿ **Accessible by design**: labeled controls, polite announcements, `focus-visible` outlines, and reduced-motion fallbacks.
- ✨ **Fun glass Aesthetic**: floating gradients, soft glassmorphism card, and animated pill controls to keep the UI lively without sacrificing contrast.

## Quick Start
1. Open `index.html` in any modern browser (Chrome, Safari, Edge, Firefox).  
   _Tip:_ For a local dev server, run `python3 -m http.server` and visit `http://localhost:8000`.
2. Type or paste text into the main field. Counts, remaining/over-limit state, and readability feedback update with every keystroke.
3. Adjust the “Character limit” input to whatever cap you need (1–10,000). The new limit is stored automatically.
4. Hit **Clear Text** to wipe the textarea and reset counts while keeping your custom limit.

## Customization Cheatsheet
| What you want | Where to tweak |
| --- | --- |
| Default max characters | `DEFAULT_MAX_LIMIT` near the bottom of `index.html` |
| Look & feel (colors, gradients) | CSS variables at the top of `index.html` |
| Readability ranges/descriptions | `describeReadability` function in `index.html` |
| Persistence keys | `STORAGE_KEY` / `LIMIT_KEY` constants in the script |

## Accessibility Notes
- Inputs/buttons expose explicit labels plus `aria-describedby` links to helper copy.
- The counts and readability blocks announce changes via `aria-live="polite"` so screen readers stay up-to-date without interrupting the user.
- `:focus-visible` outlines and high-contrast palettes ensure keyboard navigation remains obvious over the glass backdrop.
- `prefers-reduced-motion: reduce` disables the floating orb animation and smooth transitions for motion-sensitive users.

## Extending Ideas
1. Surface additional readability metrics (SMOG, Gunning Fog) beside the Flesch score.
2. Highlight complex sentences or long words inline to give actionable editing tips.
3. Export/share buttons (copy link, download text) for quick collaboration.

Have fun tailoring the component—because it’s framework-free and totally self-contained, you can slot it into landing pages, marketing tooling, or even slide decks without a build step. Happy counting! 🎉
