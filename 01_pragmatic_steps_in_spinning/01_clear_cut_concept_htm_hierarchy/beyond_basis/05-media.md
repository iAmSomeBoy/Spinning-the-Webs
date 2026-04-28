# 05 — Media (Video, Audio, iframe)

---

## `<video>` — Embedding Video

```
video                     ← media container
 ├── source               ← video file (multiple formats)
 └── (fallback text)      ← shown if browser can't play
```

```html
<video width="640" height="360" controls>
  <source src="movie.mp4"  type="video/mp4">
  <source src="movie.webm" type="video/webm">
  Your browser does not support the video tag.
</video>
```

### Key Attributes of `<video>`

| Attribute | Purpose |
|---|---|
| `controls` | Shows play/pause/volume controls |
| `autoplay` | Plays automatically (use with `muted`) |
| `muted` | Starts muted (required for autoplay in most browsers) |
| `loop` | Loops the video |
| `poster` | Image shown before video plays |
| `width` / `height` | Dimensions in pixels |
| `preload` | `auto`, `metadata`, or `none` |

```html
<video controls autoplay muted loop poster="thumbnail.jpg" width="800">
  <source src="hero.mp4" type="video/mp4">
</video>
```

### `<source>` inside video
- Self-closing, no closing tag
- Browser picks the first format it supports
- **Parent:** `<video>` or `<audio>` ONLY
- **Children:** nothing (self-closing)

---

## `<audio>` — Embedding Audio

```
audio
 ├── source               ← audio file
 └── (fallback text)
```

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg">
  <source src="song.ogg" type="audio/ogg">
  Your browser does not support audio.
</audio>
```

### Key Attributes of `<audio>`

| Attribute | Purpose |
|---|---|
| `controls` | Shows play/pause/volume |
| `autoplay` | Plays automatically |
| `muted` | Starts muted |
| `loop` | Loops the audio |
| `preload` | `auto`, `metadata`, `none` |

---

## `<iframe>` — Embedded External Content

An `<iframe>` embeds another webpage, map, video, or document inside your page.

```html
<iframe
  src="https://www.youtube.com/embed/VIDEO_ID"
  width="560"
  height="315"
  title="Video title"
  allowfullscreen>
</iframe>
```

### Common Uses

```html
<!-- YouTube video embed -->
<iframe
  src="https://www.youtube.com/embed/abc123"
  width="560"
  height="315"
  title="My Video"
  allowfullscreen>
</iframe>

<!-- Google Maps embed -->
<iframe
  src="https://www.google.com/maps/embed?..."
  width="600"
  height="450"
  loading="lazy">
</iframe>

<!-- Another HTML page -->
<iframe src="other-page.html" width="100%" height="500"></iframe>
```

### Key Attributes

| Attribute | Purpose |
|---|---|
| `src` | URL to embed |
| `width` / `height` | Size in pixels |
| `title` | Accessibility description |
| `allowfullscreen` | Allows fullscreen mode |
| `loading="lazy"` | Loads only when visible |
| `sandbox` | Restricts iframe permissions |

- **Parent:** any block element
- **Children:** fallback text only (shown if iframe fails to load)

---

## Media File Format Reference

### Video Formats
| Format | Type string |
|---|---|
| `.mp4` | `video/mp4` |
| `.webm` | `video/webm` |
| `.ogg` | `video/ogg` |

### Audio Formats
| Format | Type string |
|---|---|
| `.mp3` | `audio/mpeg` |
| `.ogg` | `audio/ogg` |
| `.wav` | `audio/wav` |

---

## Parent-Child Summary

| Tag | Valid Parents | Valid Children |
|---|---|---|
| `<video>` | any block | `<source>`, `<track>`, fallback text |
| `<audio>` | any block | `<source>`, `<track>`, fallback text |
| `<source>` | `<video>` or `<audio>` ONLY | nothing (self-closing) |
| `<iframe>` | any block | fallback text only |

---

## figure + video (best practice)

```html
<figure>
  <video controls width="600">
    <source src="demo.mp4" type="video/mp4">
  </video>
  <figcaption>Demo video showing the feature in action.</figcaption>
</figure>
```

Wrap media in `<figure>` when a caption is needed.
