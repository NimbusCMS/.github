# Brand assets

| File | Use |
|------|-----|
| `avatar.svg` | Source. Edit this, then re-render the PNGs. |
| `avatar.png` | 512×512 — the organization profile picture |
| `avatar@1024.png` | 1024×1024 — anywhere that wants more resolution |

The mark is the broom from the Nimbus admin theme
(`src/View/themes/nimbus/logo.svg` in core), on the theme's night-sky indigo
with its gold accent. Keeping them the same means the admin someone uses and
the project they find on GitHub look like the same thing.

## Colours

| Token | Hex | Where |
|-------|-----|-------|
| Indigo (deep) | `#160f3d` | background, outer |
| Indigo | `#241a5c` | background, mid |
| Violet | `#3b2a8c` | background, top-left |
| Brand | `#6d5efc` | glow |
| Gold | `#f0c24b` | broom head |
| Gold (soft) | `#f6d888` | handle, sweep trails |

## Re-rendering

GitHub does not accept SVG for avatars, so the PNGs are committed rather than
generated on demand:

```bash
docker run --rm -v "$PWD":/w -w /w alpine:latest sh -c \
  'apk add --no-cache rsvg-convert >/dev/null && \
   rsvg-convert -w 512  -h 512  avatar.svg -o avatar.png && \
   rsvg-convert -w 1024 -h 1024 avatar.svg -o avatar@1024.png'
```

## Uploading the avatar

There is no REST endpoint for an organization's profile picture — it has to be
set in the web UI:

**Organization → Settings → Profile → Profile picture → Upload a photo**,
choosing `brand/avatar.png`.
