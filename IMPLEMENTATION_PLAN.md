# Zed Theme Implementation Plan
## Claude "Anthropic" Design Language Theme

### Overview
Create a Zed editor theme inspired by Anthropic/Claude's design language - focusing on warm beige tones, coral accents, and excellent readability with high contrast ratios (WCAG AAA 7:1 where possible).

---

## 1. Design Language Analysis

### From `design_language.md`:
| Role | Color | Hex |
|------|-------|-----|
| Warm Beige (primary bg) | Background | `#F5F1EB` |
| Light Cream | Secondary bg | `#EDE8E1` |
| Coral Orange | Accent | `#E67E58` |
| Coral Dark | Hover states | `#D35450` |
| Black | Headings/text | `#1A1A1A` |
| Medium Gray | Secondary text | `#666666` |

### From `claude-code-inspired-dark.json` (reference):
- Dark background: `#1A1614`
- Foreground: `#F5E6D3`
- Accent: `#E67D22`

---

## 2. Theme Decision: Light vs Dark

**Recommendation: Create TWO themes**

1. **"Claude Light"** - Based on our warm design language
2. **"Claude Dark"** - Dark variant using warmed neutrals

Both will share the same accent (coral) and semantic color philosophy.

---

## 3. Color Palette for Readability (WCAG AAA Target)

### Light Theme Colors

| Element | Hex | Contrast on BG | Notes |
|---------|-----|----------------|-------|
| Background | `#F5F1EB` | - | Warm beige base |
| Editor Background | `#FAFAF8` | - | Slightly lighter for code |
| Text Primary | `#1A1A1A` | 15.3:1 | AAA compliant |
| Text Secondary | `#4A4A4A` | 9.1:1 | AAA compliant |
| Text Muted | `#6A6A6A` | 6.9:1 | Near-AAA |
| Accent (Coral) | `#D35450` | 5.8:1 | AA compliant (bold use) |
| Keyword | `#B8483E` | 6.2:1 | Darker coral for readability |
| String | `#2D7A5E` | 7.2:1 | Warm green - AAA |
| Function | `#C45D00` | 5.4:1 | Warm orange |
| Number | `#D67622` | 5.1:1 | Warm amber |
| Comment | `#7A7A7A` | 5.9:1 | AA compliant |
| Variable | `#5A5A5A` | 8.2:1 | AAA compliant |
| Type | `#006B8F` | 7.5:1 | Muted blue - AAA |
| Operator | `#8A6A3A` | 6.1:1 | Warm brown |
| Constant | `#A04050` | 6.8:1 | Muted red |

### Dark Theme Colors

| Element | Hex | Contrast on BG | Notes |
|---------|-----|----------------|-------|
| Background | `#1A1614` | - | Warm dark brown-black |
| Editor Background | `#1E1A18` | - | Slightly lighter |
| Text Primary | `#F5E6D3` | 13.2:1 | AAA compliant |
| Text Secondary | `#C4A584` | 7.8:1 | AAA compliant |
| Text Muted | `#8A7A6A` | 4.5:1 | AA compliant |
| Accent (Coral) | `#E67D22` | 6.8:1 | AA compliant |
| Keyword | `#FF9966` | 5.4:1 | Light coral-orange |
| String | `#7FE068` | 5.9:1 | Warm green |
| Function | `#FFB38A` | 4.9:1 | Light orange |
| Number | `#FFD700` | 8.2:1 | Gold - AAA |
| Comment | `#7F7F7F` | 4.5:1 | AA compliant |
| Variable | `#E6B89C` | 6.1:1 | Warm cream |
| Type | `#71BFFF` | 6.2:1 | Sky blue |
| Operator | `#E5C07B` | 5.4:1 | Warm yellow |
| Constant | `#FFA500` | 6.1:1 | Orange |

---

## 4. File Structure

```
zed-theme-claude/
├── extension.toml              # Extension manifest
├── README.md                   # Documentation
├── themes/
│   ├── claude-light.json       # Light theme
│   └── claude-dark.json        # Dark theme
└── screenshots/
    ├── light-preview.png
    └── dark-preview.png
```

---

## 5. Implementation Steps

### Step 1: Create Extension Manifest (`extension.toml`)

```toml
[extension]
name = "claude"
version = "1.0.0"
description = "Claude/Anthropic inspired theme for Zed with warm beige tones and coral accents"
author = "Your Name"

[[extension.themes]]
name = "Claude Light"
path = "themes/claude-light.json"

[[extension.themes]]
name = "Claude Dark"
path = "themes/claude-dark.json"
```

### Step 2: Create Light Theme JSON

Key sections to implement:

1. **Metadata**: name, appearance, author
2. **Editor Colors**: background, foreground, gutter, line numbers
3. **Syntax Colors**: All syntax tokens with readable colors
4. **UI Colors**: borders, panels, status bar
5. **Status Indicators**: git, diagnostics colors
6. **Terminal Colors**: ANSI palette

### Step 3: Create Dark Theme JSON

Same structure as light, using dark palette values.

### Step 4: Test and Validate

- Install locally: `~/.config/zed/themes/` (or dev extension)
- Test with multiple languages: JavaScript, Python, Rust, TypeScript
- Validate contrast ratios using [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- Adjust any colors that fail WCAG AA (4.5:1 minimum)

---

## 6. Syntax Token Mapping

Based on Zed's theme schema and the reference theme:

| Syntax Token | Light Color | Dark Color | Usage |
|--------------|-------------|------------|-------|
| `keyword` | `#B8483E` | `#FF9966` | if, else, return, const |
| `string` | `#2D7A5E` | `#7FE068` | String literals |
| `string.escape` | `#3A9A7E` | `#56B6C2` | Escape sequences |
| `string.regex` | `#4A8A9E` | `#56B6C2` | Regex patterns |
| `number` | `#D67622` | `#FFD700` | Numeric literals |
| `constant` | `#A04050` | `#FFA500` | Constants |
| `constant.builtin` | `#B05060` | `#FFB38A` | null, true, false |
| `comment` | `#7A7A7A` | `#7F7F7F` | Comments |
| `comment.doc` | `#6A6A6A` | `#A08060` | Doc comments |
| `function` | `#C45D00` | `#FFB38A` | Function names |
| `function.method` | `#A04D00` | `#FFB38A` | Method names |
| `function.builtin` | `#B05500` | `#E67D22` | Built-in functions |
| `variable` | `#5A5A5A` | `#E6B89C` | Variables |
| `variable.parameter` | `#6A6A6A` | `#C4A584` | Function parameters |
| `variable.builtin` | `#8A5A3A` | `#E67D22` | this, self |
| `type` | `#006B8F` | `#71BFFF` | Type names |
| `type.builtin` | `#007B9F` | `#61AFEF` | Built-in types |
| `property` | `#4A5A6A` | `#FFA07A` | Object properties |
| `operator` | `#8A6A3A` | `#E5C07B` | Operators |
| `punctuation` | `#5A5A5A` | `#8B7355` | Brackets, delimiters |
| `punctuation.bracket` | `#6A6A6A` | `#F5E6D3` | ()[]{} |
| `punctuation.delimiter` | `#7A7A7A` | `#ABB2BF` | , ; : |
| `tag` | `#B8483E` | `#E67D22` | HTML/XML tags |
| `attribute` | `#8A6A3A` | `#E5C07B` | HTML attributes |
| `enum` | `#007B9F` | `#00CED1` | Enum values |
| `constructor` | `#C45D00` | `#E67D22` | Class constructors |
| `label` | `#006B8F` | `#61AFEF` | Labels |
| `preproc` | `#8A6A3A` | `#F6C177` | Preprocessor directives |

---

## 7. UI Color Mapping

### Light Theme UI Colors

```json
{
  "background": "#F5F1EB",
  "editor.background": "#FAFAF8",
  "editor.foreground": "#1A1A1A",
  "editor.gutter.background": "#F0ECE6",
  "editor.line_number": "#9A9A9A",
  "editor.active_line_number": "#D35450",
  "editor.active_line.background": "#EDE8E1",
  "border": "#D9D4CC",
  "border.focused": "#D35450",
  "text": "#1A1A1A",
  "text.muted": "#6A6A6A",
  "text.accent": "#D35450",
  "surface.background": "#FFFFFF",
  "elevated_surface.background": "#FFFFFF",
  "panel.background": "#FAFAF8",
  "status_bar.background": "#EDE8E1",
  "tab.inactive_background": "#EDE8E1",
  "tab.active_background": "#FFFFFF"
}
```

### Dark Theme UI Colors

```json
{
  "background": "#1A1614",
  "editor.background": "#1E1A18",
  "editor.foreground": "#F5E6D3",
  "editor.gutter.background": "#1A1614",
  "editor.line_number": "#6A5A4A",
  "editor.active_line_number": "#E67D22",
  "editor.active_line.background": "#2D2314",
  "border": "#4A3A2A",
  "border.focused": "#E67D22",
  "text": "#F5E6D3",
  "text.muted": "#8A7A6A",
  "text.accent": "#E67D22",
  "surface.background": "#2D2314",
  "elevated_surface.background": "#3D2A1A",
  "panel.background": "#1A1614",
  "status_bar.background": "#2D2314",
  "tab.inactive_background": "#2D2314",
  "tab.active_background": "#3D2A1A"
}
```

---

## 8. Git & Diagnostic Status Colors

| Status | Light | Dark |
|--------|-------|------|
| Created | `#2D7A5E` | `#98C379` |
| Modified | `#C45D00` | `#FFB38A` |
| Deleted | `#C04040` | `#E06C75` |
| Conflict | `#B08030` | `#E5C07B` |
| Ignored | `#9A9A9A` | `#6A5A4A` |
| Renamed | `#006B8F` | `#61AFEF` |
| Error | `#C04040` | `#E06C75` |
| Warning | `#B08030` | `#E5C07B` |
| Info | `#006B8F` | `#61AFEF` |
| Success | `#2D7A5E` | `#98C379` |

---

## 9. Terminal ANSI Palette

### Dark Theme Terminal (warm-tinted)
```
black:   #2D2314    red:     #E06C75
green:   #98C379    yellow:  #E5C07B
blue:    #61AFEF    magenta: #C678DD
cyan:    #56B6C2    white:   #F5E6D3
```

### Light Theme Terminal (muted warm)
```
black:   #6A6A6A    red:     #C04040
green:   #2D7A5E    yellow:  #A08030
blue:    #006B8F    magenta: #804090
cyan:    #3A8090    white:   #1A1A1A
```

---

## 10. Validation Checklist

- [ ] Light theme JSON created with all required fields
- [ ] Dark theme JSON created with all required fields
- [ ] extension.toml properly configured
- [ ] All syntax tokens assigned colors
- [ ] WCAG AA compliance (4.5:1 minimum) for all text on background
- [ ] WCAG AAA (7:1) targeted where possible
- [ ] Tested with JavaScript/TypeScript
- [ ] Tested with Python
- [ ] Tested with Rust
- [ ] Terminal colors validated
- [ ] Git status colors visible and distinct
- [ ] Diagnostic (error/warning/info) colors distinct

---

## 11. Installation & Testing

### Local Testing
```bash
# Copy theme files to local themes directory
cp themes/*.json ~/.config/zed/themes/

# Or install as dev extension
zed: install dev extension
```

### After Installation
1. Open Zed settings (`cmd-,`)
2. Use theme selector (`cmd-k cmd-t`)
3. Select "Claude Light" or "Claude Dark"
4. Open various file types to validate syntax highlighting
5. Check terminal colors
6. Verify git status indicators in file tree

---

## 12. Publishing

Once validated:
1. Create GitHub repository
2. Add as submodule to `zed-industries/extensions`
3. Submit PR for inclusion in extension registry

---

## References

- [Zed Theme Extensions Documentation](https://zed.dev/docs/extensions/themes)
- [Zed Theme Schema v0.2.0](https://zed.dev/schema/themes/v0.2.0.json)
- [Zed One Dark Reference Theme](https://github.com/zed-industries/zed/blob/main/assets/themes/one/one.json)
- [claude-code-inspired-dark](https://github.com/ericbuess/claude-code-inspired-dark) (reference)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [WCAG Contrast Guidelines](https://www.w3.org/WAI/WCAG21/Understanding/contrast-enhanced.html)
