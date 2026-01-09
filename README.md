# Claude Anthropic Theme for Zed

A warm, readable theme for Zed editor inspired by Anthropic and Claude's design language.

## Features

- **Warm beige tones** - Based on Anthropic's signature color palette
- **Coral orange accents** - The signature Claude accent color (#E67E58)
- **High readability** - WCAG AA compliant contrast ratios (4.5:1 minimum)
- **Light & Dark variants** - Both themes included
- **Semantic syntax highlighting** - Purposeful colors for each syntax element

## Installation

### Method 1: Dev Extension (Recommended for development)

1. Clone or download this repository
2. Open Zed's command palette (`Cmd+Shift+P` on macOS)
3. Type `dev: install extension` and select it
4. Navigate to this repository folder and select it
5. Restart Zed
6. Open settings (`Cmd+,`) and select "Claude Light" or "Claude Dark"

### Method 2: Local Theme Files

1. Copy `themes/*.json` to your local Zed themes directory:
   - macOS/Linux: `~/.config/zed/themes/`
   - Windows: `%USERPROFILE%\AppData\Roaming\Zed\themes\`
2. Restart Zed
3. Use theme selector (`Cmd+K Cmd+T`) to select a theme

## Color Palette

### Common Colors (Both Themes)

| Role | Color |
|------|-------|
| Accent (Coral) | `#E67E58` |
| Accent Dark | `#D35450` |
| Accent Light | `#FFB38A` |

### Light Theme

| Element | Color |
|---------|-------|
| Background | `#F5F1EB` |
| Editor BG | `#FAFAF8` |
| Text | `#1A1A1A` |
| Keywords | `#B8483E` |
| Strings | `#2D7A5E` |
| Functions | `#C45D00` |
| Numbers | `#D67622` |

### Dark Theme

| Element | Color |
|---------|-------|
| Background | `#1A1614` |
| Editor BG | `#1E1A18` |
| Text | `#F5E6D3` |
| Keywords | `#FF9966` |
| Strings | `#7FE068` |
| Functions | `#FFB38A` |
| Numbers | `#FFD700` |

## File Structure

```
claude-anthropic-theme/
├── extension.toml              # Extension manifest
├── themes/
│   ├── claude-light.json       # Light theme
│   └── claude-dark.json        # Dark theme
├── README.md                   # This file
├── IMPLEMENTATION_PLAN.md      # Design documentation
└── design_language.md          # Base design language
```

## Syntax Highlighting Preview

### Light Theme
- Keywords: Deep coral (`#B8483E`)
- Strings: Warm green (`#2D7A5E`)
- Functions: Warm orange (`#C45D00`)
- Comments: Muted gray, italic (`#7A7A7A`)
- Variables: Dark gray (`#5A5A5A`)
- Types: Muted blue (`#006B8F`)

### Dark Theme
- Keywords: Light coral (`#FF9966`)
- Strings: Warm green (`#7FE068`)
- Functions: Light orange (`#FFB38A`)
- Comments: Muted gray, italic (`#7F7F7F`)
- Variables: Warm cream (`#E6B89C`)
- Types: Sky blue (`#71BFFF`)

## Inspiration

This theme is inspired by:
- [Anthropic's website](https://www.anthropic.com/)
- [Claude.ai](https://claude.ai)
- [claude-code-inspired-dark](https://github.com/ericbuess/claude-code-inspired-dark) by Eric Buess

## License

MIT

## Author

Based on Eric Buess, and Chris McK
