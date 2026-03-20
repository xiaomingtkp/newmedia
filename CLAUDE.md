# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Setup

This is a **pure static HTML application** with no build tools or dependencies. To run:

```bash
# Open in browser (no server required for local files)
open index.html
# or simply open the index.html file in any web browser
```

## Project Structure

```
web-xhs-note-generator/
├── index.html              # Landing page (entry point)
├── views/
│   ├── note.html          # Main editor (Markdown-based)
│   └── cover.html         # Cover generator
├── fonts/
│   ├── fonts.css          # Font definitions (Noto Sans SC, Inter)
│   ├── Inter-Regular.ttf
│   ├── Inter-Bold.ttf
│   ├── NotoSansSC-Regular.ttf
│   └── NotoSansSC-Bold.ttf
└── favicon.svg
```

## Architecture Overview

### Multi-Page Application

Unlike what the original CLAUDE.md suggests, this is a **multi-page static application** with two main pages:

1. **[index.html](index.html)** - Landing page with cards linking to tools
2. **[views/note.html](views/note.html)** - Main editor with three-panel layout
3. **[views/cover.html](views/cover.html)** - Cover generator

### Key Components (note.html)

1. **Three-Panel Layout**
   - Left panel: Markdown editor for content creation
   - Center: Live preview canvas with zoom/viewport controls
   - Right panel: Configuration parameters (themes, text, images)

2. **Theme System** (4 styles defined in JS)
   - `minimal`: Light blue background with dark blue text
   - `serif`: Book-inspired style with serif fonts
   - `acid`: High-contrast acid green theme
   - `tech`: Dark tech theme with grid background

3. **Markdown Processing**
   - Uses `marked.js` for Markdown parsing
   - Custom image renderer supporting `img:{id}` syntax for local images
   - `@---` separator for multi-page pagination

4. **State Management**
   - All state in `state` object (styleId, titleSize, bodySize, coverImage, bodyImages)
   - `localStorage` persistence across sessions
   - URL parameter support (`?title=...&content=...`)

5. **Image Handling**
   - Cover image upload (localized to card)
   - Body images through paste (Ctrl+V) or upload button
   - Base64 storage in `state.bodyImages` object
   - Image manager UI for managing embedded images

6. **Export Functionality**
   - `html-to-image` library for single card export
   - `JSZip` + `FileSaver` for batch ZIP export
   - 2x pixelRatio for high-quality JPG output

### Font Localization

Fonts are served locally from `fonts/` directory (see [fonts/fonts.css](fonts/fonts.css)):
- Inter (Regular, Bold, Bold 800)
- Noto Sans SC (Regular, Medium 500, Bold 700, 900)
- Noto Serif SC (fallback to Noto Sans SC)

This avoids CORS issues with `html-to-image` and network dependencies.
