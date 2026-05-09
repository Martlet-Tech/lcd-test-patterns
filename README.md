# LCD Test Patterns

[![Pages](https://img.shields.io/badge/GitHub-Pages-blue)](https://martlet-tech.github.io/lcd-test-patterns/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

**Web-based LCD display test image generator** — a static HTML/JS port of the C# Windows Forms application *TestPictrueGenerator*.

Designed for LCD debug engineers, display driver developers, and hardware validation teams. No server, no build step, no dependencies — open `index.html` in any browser or use the GitHub Pages hosted version.

## Features

### Test Pattern Generation
| Category | Patterns |
|----------|----------|
| **Detail Mode** | Black Frame, White, Red, Green, Blue, Black, 50% Gray, Gray Gradient + Crosstalk, Color Bar, Sample Picture |
| **Simple Mode** | Frame, White, Color Bar, Gray Gradient, Black (5-image subset) |
| **Common** | Scale/Ruler, Frame + Triangle, Chess Board, H-Line/V-Line Stripes, AllRGB |
| **CrossTalk** | HV (center block), Horizontal (side blocks), Vertical (top/bottom blocks) |
| **Flicker** | Block pattern, Horizontal line, Vertical line — configurable colors |
| **Gradient** | 8-direction configurable gradient with custom start/end colors |

### DPI Timing Calculator
- Horizontal/Vertical timing parameter input (HSW, HBP, HACT, HFP, VSW, VBP, VACT, VFP)
- Pixel clock calculation from timing + FPS
- DSI bitrate calculation (lanes × color bits)
- Config script generation with polarity settings

### Output
- PNG / JPEG download
- Batch ZIP download (all selected patterns)
- Full-resolution canvas preview with click-to-zoom
- Cut Panel mode for partial-screen displays

## Usage

### Online
Visit **[https://martlet-tech.github.io/lcd-test-patterns/](https://martlet-tech.github.io/lcd-test-patterns/)**

### Offline
```bash
git clone https://github.com/Martlet-Tech/lcd-test-patterns.git
cd lcd-test-patterns
# Open index.html in your browser
start index.html
```

No build step required — it's a single static HTML file with inline CSS and JavaScript.

## Pattern Description

1. **Black Frame** — White background with a black rectangle (or circle) to check screen boundaries and light bleed
2. **Pure Colors** (White/Red/Green/Blue/Black/Gray) — Detect dead/stuck sub-pixels, check uniformity
3. **Gray Gradient + Crosstalk** — Diagonal gradient with white center rectangle to test gray-level crosstalk
4. **Color Bar** — R/G/B/White/CYM linear gradients for color reproduction assessment
5. **Scale/Ruler** — Crosshair ruler with tick marks at 2/10/50/100 pixel intervals for pixel mapping
6. **Chess Board** — Adjustable grid size for contrast, response time, and moiré evaluation
7. **H-Line / V-Line** — Alternating horizontal/vertical stripes for line defect detection
8. **CrossTalk** — Black rectangles on white background to measure voltage coupling between regions
9. **Flicker** — Alternating color patterns for Vcom/flicker adjustment
10. **AllRGB** — Every pixel gets a unique color (full 24-bit color space distribution)

## Relationship to Original Project

This is a web port of [TestPictrueGenerator](https://gitee.com/martlet/TestPictrueGrenerator) (Gitee), a C# Windows Forms application by Martlet Zhu. The original C# source code is preserved in the `Sources/` directory of that repository.

## Browser Support

Chrome, Firefox, Edge, Safari — any modern browser with Canvas API support.

## License

MIT
