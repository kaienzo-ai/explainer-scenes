# explainer-scenes

> 8 reusable explainer overlay patterns for short-form vertical video (TikTok / Reels / Shorts).
> CSS + inline SVG. Self-contained. Drag any `.html` into a browser to preview.

Most short-form explainer reels reach for the same handful of visual rhetorical
moves over and over: *here's a pipeline*, *here's a fork in the road*, *here's a
before/after*, *here's a single number that does the heavy lifting*. This repo
turns those moves into 8 named, reusable scene types — picked by **rhetorical
fit**, not by what looks cool.

The point is that *which scene you reach for is a decision*, not a style choice.
A `compare` scene says something different than a `flow` scene, even if both could
hold the same information. Naming them gives you a vocabulary.

The demo content is intentionally **DevOps / CI-CD flavored**, because that's
the audience I've been thinking about while writing this. The patterns themselves
are content-agnostic.

---

## The 8 types

| Type | Rhetorical move | Use when… |
|---|---|---|
| [`flow`](flow.html) | Sequence / pipeline | The argument is "A leads to B leads to C" |
| [`decision`](decision.html) | Branch / fork | One condition forks into two outcomes |
| [`terminal`](terminal.html) | Receipt / proof | You want to say "here's what actually happened" |
| [`compare`](compare.html) | Before vs after / bad vs good | Two states the viewer should weigh against each other (left = the worse one) |
| [`stat`](stat.html) | One number does the work | A single quantity carries the whole point |
| [`checklist`](checklist.html) | Discrete steps to verify | A finite list the viewer should mentally walk through |
| [`quote`](quote.html) | Borrowed authority | Someone else said it better; the source matters |
| [`meter`](meter.html) | Position on a scale | The point is *where on a range* something sits |

Open [`index.html`](index.html) for a side-by-side gallery of all eight.

### Same patterns, different domains

The eight scenes above use **DevOps / CI-CD demo content**. The patterns
themselves are domain-agnostic — see [`examples/`](examples/) for four of
them re-applied to **creator-economy / AI-content / workflow** topics
(same CSS, different copy):

- [`examples/stat-creator.html`](examples/stat-creator.html) — creator metric (views, reach)
- [`examples/compare-workflow.html`](examples/compare-workflow.html) — manual editing vs AI pipeline
- [`examples/flow-content.html`](examples/flow-content.html) — brief → script → render → publish
- [`examples/quote-creator.html`](examples/quote-creator.html) — ship-fast ethos (Reid Hoffman)

---

## Conventions baked in

A few opinionated defaults I've found matter more than they look:

- **`compare` puts the worse option on the left.** Readers scan left-to-right;
  ending on the *better* option lands the resolution where the eye stops.
- **`terminal` carries no label or title.** A label above a terminal mockup
  breaks the receipt-style "here's what actually happened" frame. The terminal
  *is* the evidence; framing it is a tell.
- **`decision` auto-fits text.** Branch labels are often long phrases that don't
  fit a fixed-width box. Each label sizes itself down rather than truncating —
  losing words is worse than losing one font weight.
- **9:16 by default.** All scenes are designed for vertical short-form. Scaling
  to 16:9 is possible but tends to leave dead space; better to redesign per
  aspect ratio than to letterbox.
- **No external dependencies.** No webfonts, no CSS frameworks, no JS. Every
  scene renders from system fonts and inline SVG so you can fork a single
  `.html` file and drop it into any pipeline.

---

## How to use

**Preview locally:**

```sh
git clone https://github.com/kaienzo-ai/explainer-scenes
cd explainer-scenes
open flow.html    # or any other scene file
```

Or just open `index.html` in a browser for the gallery.

**Integrate into a video pipeline:**

The intended use is as overlays on top of vertical video. Render each scene
as a transparent or solid-background frame at 1080×1920, then composite over
your footage with your renderer of choice (ffmpeg, Remotion, After Effects,
or — in my case — a local Whisper-driven pipeline that picks the scene type
from transcript shape).

Adapt the styling per brand. The colors and typography here are opinionated —
editorial palette (cream `#f4efe1` + deep red `#7d1414`) and condensed display
type (Anton). Override the CSS custom properties (`--cream`, `--red`,
`--ink`, `--rule`) and swap the Google Fonts import to match your own brand.

Fonts used: [Anton](https://fonts.google.com/specimen/Anton) (display),
[Inter](https://fonts.google.com/specimen/Inter) (body), [JetBrains
Mono](https://fonts.google.com/specimen/JetBrains+Mono) (terminal only),
[Playfair Display](https://fonts.google.com/specimen/Playfair+Display)
(quote only). All from Google Fonts.

---

## License

MIT — fork freely, adapt freely, no attribution required (but appreciated).

---

## About

Built by Kai ([@kaienzo.ai](https://instagram.com/kaienzo.ai)) — AI Creative
Director / Filmmaker. I run a multi-brand short-form pipeline that ships
weekly. These 8 scene types came out of needing a vocabulary for *which kind
of explainer reaches viewers when*.

If you found this useful, the [companion blog post](#) walks through how to
pick a scene type from a transcript, with examples. *(Link added when post
goes live.)*

Contact: `innikreatif@gmail.com`
