# Blue Rose Boutique — hero (work in progress)

Client preview for **Blue Rose Boutique**, centro estetico, via Roma 242, Olbia (SS).
Owner-operator: Veronica Rosso.

This is the **hero section only**. The rest of the page is intentionally not built
yet — the hero is being signed off first.

## Run it

Any static server; there is no build step.

```bash
python -m http.server 8322
```

Then open <http://localhost:8322>.

## What's here

| Path | |
|---|---|
| `index.html` | The whole page: markup, styles and script inline |
| `media/hero@2x.mp4` | Hero loop, 1280×720, desktop |
| `media/hero.mp4` | Hero loop, 854×480, phones |
| `media/hero-poster.jpg` | Poster frame + fallback when video can't autoplay |
| `og.png` | Link preview card for WhatsApp / Instagram / Facebook |

## Notes

**The hero loop** is the client's `Hero video_classic.mp4`, slowed to 1.55× and
closed into a seamless loop: the final 1.3s is cross-faded back over the opening,
so the clip ends on the frame it begins on. Measured seam difference is ~1%
luminance, invisible in motion.

**Sharpness.** The plate occupies the right 60% of the viewport rather than the
full width, and ships at 2×. This keeps the video *downscaled* (≈0.91×) at every
common desktop width instead of stretched — full-bleed would mean a ~1.9× blow-up
on a 1600px screen.

**Colours** are sampled from the client's own comp (`BLue_rose hero_V2.png`),
taking the darkest decile of each text band so antialiasing doesn't skew the value.

## Known issues

- **Button label**: white on `#A79275` measures **3.0:1**, below the 4.5:1 WCAG AA
  minimum for text this size. Shipped as drawn in the comp. Fix is either a deeper
  fill (`#84714F`, 4.7:1) or a dark label on the existing tan (5.1:1).
- **`BOUTIQUE`** in the wordmark is `2.77:1`. Part of the logo lockup, which WCAG
  exempts, so defensible as-is.
- Nav links are placeholders (`#`) until the remaining sections exist.

## Still needed from the client

Session duration · number of sessions in the Percorso and its price · make and
model of the device · opening hours · P.IVA · link to the Google reviews profile.
All omitted rather than invented.
