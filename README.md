# AR Stickers: web version (no app)

```
index.html            ← the AR page
assets/stickers.glb   ← your Blender export (all 5 characters)
targets/01…05.png     ← sticker images used for tracking
targets/targets.mind  ← YOU MAKE THIS (step 1)
```

## 1. Compile the tracking file (one time)
1. Open the MindAR compiler: https://hiukim.github.io/mind-ar-js-doc/tools/compile
2. Drag the images in **this exact order**: 01-butterfly, 02-egg, 03-star, 04-clover, 05-poop
   - Best results: use your **original print-resolution artwork** (the same files you send to the printer), cropped to the sticker's cut line, instead of the PNGs here, which were cropped from a screenshot.
3. Click **Start**, then download the result, rename it `targets.mind` and put it in `targets/`.

If you add or reorder stickers, recompile and update the `STICKERS` list at the top of `index.html` to match.

## 2. Put it online (free, HTTPS is required for the camera)
**GitHub Pages:** new repo → upload this folder → Settings → Pages → Branch: main → Save.
Your link will be `https://<username>.github.io/<repo>/`.
(Netlify Drop also works: drag the folder onto app.netlify.com/drop.)

## 3. Test
Open the link on your phone, tap start, and point at a printed sticker (or at the sticker on your laptop screen).

## 4. QR code
Make a QR code for the link and print it on the sticker backing or packaging.

## Tweaking (top of index.html)
| setting | what it does |
|---|---|
| `size` | character size relative to the sticker width |
| `lift` | how far it floats off the sticker |
| `rotY` | turns the character (180 = faces the camera with your current export) |
| `maxTrack` | how many stickers can animate at the same time |

## Tips
- Matte stickers track much better than glossy ones (glare breaks tracking).
- iPhone: open the link in Safari or Chrome, not inside Instagram/TikTok.
- In Blender, a new action has to be pushed to an NLA track, or it won't be exported.
