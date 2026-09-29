# 墨 Sumi

**Play it: [jcedrik.github.io/sumi](https://jcedrik.github.io/sumi/)**

A small timing game I built around Japanese ink (sumi-e) aesthetics. Ink strokes fall toward a stone in the center, and you tap the moment a stroke hits the ring. The closer your timing, the cleaner the splash: a perfect hit lands as a tight blot, a late one sprays across the paper.

I made it as a break from heavier projects, but I wanted it to actually look good and feel tight, not just be a generic canvas demo.

## How it works

It's one `index.html`. HTML canvas, plain JavaScript, no framework and no build step, so it loads instantly and deploys anywhere.

- The render loop runs on `requestAnimationFrame` and redraws the stone, the incoming strokes, the splash particles and the ripple feedback every frame.
- Timing is judged by measuring how far a tapped stroke is from the target ring, then turning that into an accuracy value graded perfect / good / ok.
- The ink splash is a tiny particle system. Accuracy controls how many droplets spawn and how wide they spray, so the visual tells you how well you timed it.
- Difficulty ramps with your score: strokes spawn faster and fall quicker as you climb.
- You get three lives, lost when a stroke reaches the stone untapped.

## Controls

Tap, click, or press Space to strike.

## Run locally

No build needed. Open the file:

```bash
start index.html     # Windows
open index.html      # macOS
```

Or serve it, which avoids any file:// quirks:

```bash
python -m http.server 8000
# then open http://localhost:8000
```

## Deploy

It's a static page, so any static host works. With Vercel:

```bash
npm i -g vercel
vercel
```

No config needed.

## Design notes

I kept the palette tight on purpose: aged paper (#ece7dc), ink (#1a1815), and one vermilion accent (#b23a2f) for the seal, the combo counter and your lives. Type is monospace throughout. The splash is the one loud element. Everything else stays quiet so the splash carries the personality.

## License

MIT
