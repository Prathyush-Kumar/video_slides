# Pod Slideshow

A single web page that plays a PowerPoint deck as an automatic slideshow. The link chooses which pod's deck plays.

## How it works

- Open `index.html?pod=N` (N = 1 to 7).
- The page loads `podN.pptx`, converts it to HTML in the browser, and shows one slide at a time.
- Every 5 seconds it fades to the next slide, and loops after the last one.
- There are no buttons or controls on screen.

## Files (all in the same folder)

```
index.html
pod1.pptx
pod2.pptx
...
pod7.pptx
```

## Links

| Pod | Link |
|-----|------|
| 1 | `https://<your-site>/?pod=1` |
| 2 | `https://<your-site>/?pod=2` |
| ... | ... |
| 7 | `https://<your-site>/?pod=7` |

If the pod number is missing or not 1 to 7, or the PPTX file is missing or unreadable, the page shows **"No presentations available"**.

## Settings

Edit the top of the `<script>` in `index.html`:

| Setting | What it does | Default |
|---------|--------------|---------|
| `PODS` | File name for each pod | `pod1.pptx` to `pod7.pptx` |
| `SECONDS` | Time per slide (includes the fade) | `5` |
| `FADE_MS` | Fade duration in milliseconds | `700` |
| `SLIDE_W` / `SLIDE_H` | Slide shape: `960 x 540` for widescreen, `960 x 720` for 4:3 | `960 x 540` |

## Requirements

- The page must be served over http(s) (GitHub Pages, Cloudflare, etc.). Opening `index.html` directly from a computer will not work.
- The device needs internet access, because the converter library (`pptx-preview` 1.0.7) loads from the jsDelivr CDN.


## Updating a deck

Replace the `podN.pptx` file in the folder. No other change is needed.
