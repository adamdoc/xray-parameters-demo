# X-ray Imaging Parameters — Interactive Demo

An interactive, single-file web demo showing how three key parameters of a
projection X-ray setup shape the recorded image. Everything runs client-side in
a single `index.html` — no build step, no dependencies.

**Live demo:** _(add your GitHub Pages URL here once published)_

## What it shows

A top-down view of a simple X-ray setup (source → sample → detector) next to a
simulated detector image. Drag the sliders and watch the trade-offs:

| Parameter | Effect | Trade-off |
|-----------|--------|-----------|
| **Source size** (focal spot) | Geometric sharpness | Smaller = sharper edges; larger = more penumbra blur (but can deliver more flux) |
| **Source-to-sample distance** | Magnification | Closer to the source = higher magnification, but the penumbra grows so the image also blurs |
| **Exposure / dose** (mAs) | Brightness & noise | More photons = brighter and cleaner (noise ∝ 1/√photons), but more dose to the sample; too much burns out detail |

### The physics

- Magnification `M = SDD / SOD`
- Geometric unsharpness (penumbra) `U = focal_spot × (M − 1)`
- Image noise `∝ 1 / √(photon count)`, with photon count driven by exposure
- `SDD` (source-to-detector distance) is fixed at 100 cm

## Running locally

Just open `index.html` in any modern browser — that's it. Or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Hosting on GitHub Pages

In the repo: **Settings → Pages → Source: `main` branch / root**. The site goes
live at `https://<username>.github.io/<repo>/`.

## License

MIT
