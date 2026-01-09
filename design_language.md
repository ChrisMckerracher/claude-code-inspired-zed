# Anthropic/Claude Design Language

## Overview

This design language captures the visual identity of Anthropic and Claude.ai - characterized by warmth, minimalism, and thoughtful restraint. The aesthetic balances professional credibility with approachability through warm neutrals and bold accent colors.

## Color Palette

### Primary Colors

| Color Name | Hex | Usage |
|------------|-----|-------|
| Near White | `#FDFCFB` | Editor background |
| Warm Beige | `#F5F1EB` | Primary background |
| Light Cream | `#EDE8E1` | Secondary background, cards, active elements |
| Off-White | `#FAF8F5` | Elevated surfaces (terminal, toolbar, input, active tab) |
| Cream | `#FAF9F5` | Gutter background |
| Light Gray | `#F0ECE6` | Scrollbar track, subtle backgrounds |

### Accent Colors

| Color Name | Hex | Usage |
|------------|-----|-------|
| **Bold Orange** | `#C66140` | Primary CTAs, keywords, highlights |
| Coral Orange | `#E67E58` | Secondary accents, UI elements |
| Coral Dark | `#D35450` | Hover states |
| Warm Yellow | `#F4C542` | Tertiary accents |

### Text Colors

| Color Name | Hex | Usage |
|------------|-----|-------|
| Black | `#1A1A1A` | Headings, primary text |
| Dark Gray | `#2D2D2D` | Body text |
| Medium Gray | `#666666` | Secondary text, labels |
| Light Gray | `#999999` | Disabled, placeholders |

### Borders & Dividers

| Color Name | Hex | Usage |
|------------|-----|-------|
| Border | `#E5E0D8` | Component borders |
| Divider | `#D9D4CC` | Section dividers, hover states |
| Border Variant | `#CCC8C0` | De-emphasized borders |
| Border Muted | `#C9C4BC` | Indent guides, scrollbars |
| Border Dark | `#B9B4AC` | Scrollbar hover |
| Border Faded | `#D0CCC4` | Ghost element selected |

### Syntax Colors (Light Theme)

| Color Name | Hex | Usage |
|------------|-----|-------|
| String Green | `#2D7A5E` | String literals |
| String Escape | `#3A9A7E` | Escape sequences |
| String Regex | `#4A8A9E` | Regex patterns |
| Function Orange | `#E67E58` | Function names |
| Function Dark | `#D35450` | Built-in functions |
| Function Method | `#C45D00` | Method names (italic) |
| Brown | `#8A6A3A` | Attributes, operators, preproc |
| Brown Dark | `#A07040` | Directives, symbols |
| Comment Gray | `#7A7A7A` | Comments (italic) |
| Comment Dim | `#6A6A6A` | Doc comments (italic) |
| Variable Gray | `#5A5A5A` | Variables |
| Variable Muted | `#6A6A6A` | Parameters (italic) |
| Property Slate | `#4A5A6A` | Object properties |
| Punctuation Gray | `#6A6A6A` | Punctuation |
| Bracket Gray | `#5A5A5A` | Brackets |
| Delimiter Gray | `#7A7A7A` | Delimiters |
| Type Blue | `#006B8F` | Type names |
| Type Bright | `#007B9F` | Built-in types, enums |
| Label Blue | `#006B8F` | Labels |
| Link Cyan | `#3A8090` | URIs (underline) |
| Hint Purple | `#8060B0` | Hints |
| Primary Orange | `#C66140` | Primary syntax |

### Status Colors

| Color Name | Hex | Usage |
|------------|-----|-------|
| Success Green | `#2D7A5E` | Created, success |
| Modified Orange | `#E67E58` | Modified files |
| Error Red | `#C04040` | Deleted, errors |
| Warning Tan | `#B08030` | Conflicts, warnings |
| Info Blue | `#006B8F` | Renamed, info |
| Ignored Gray | `#9A9A9A` | Ignored files |
| Variant Pink | `#B05060` | Variant types |

### Additional UI Colors

| Color Name | Hex | Usage |
|------------|-----|-------|
| Surface | `#FAFAF8` | Panel surfaces |
| Element Cream | `#F5F0EB` | Active/selected elements |
| Predictive Gray | `#8A7A9A` | Predictive text |
| Disabled Gray | `#AAAAAA` | Disabled text |
| Icon Gray | `#5A5A5A` | Default icons |
| Icon Muted | `#9A9A9A` | Muted icons |
| Line Number Gray | `#9A9A9A` | Line numbers |

## Typography

### Font Families

```
Headings: "Playfair Display", "Georgia", serif
Body: "Inter", "Helvetica Neue", sans-serif
Mono: "SF Mono", "Menlo", monospace
```

### Type Scale

| Level | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| Display | 48px | 600 | 1.1 | Hero titles |
| H1 | 36px | 600 | 1.2 | Page titles |
| H2 | 28px | 600 | 1.3 | Section headers |
| H3 | 22px | 600 | 1.4 | Subsections |
| Body | 16px | 400 | 1.5 | Body text |
| Small | 14px | 400 | 1.5 | Captions, labels |
| XSmall | 12px | 400 | 1.4 | Fine print |

### Letter Spacing

- Headings: `-0.02em` (slightly tight)
- Body: `0` (normal)
- All caps/Buttons: `0.05em` (slightly expanded)

## Spacing Scale

```
4px   - xs
8px   - sm
12px  - md
16px  - lg
24px  - xl
32px  - 2xl
48px  - 3xl
64px  - 4xl
96px  - 5xl
```

## Layout Principles

### Container
- Max width: `1200px` for main content
- Centered with `auto` margins
- Padding: `24px` on mobile, `48px` on desktop

### Grid
- 12-column grid
- Gutter: `24px`
- Breakpoints: 640px, 1024px, 1280px

### Whitespace
- Generous padding between sections (`96px`+)
- Internal padding: `16px` (mobile), `24px` (desktop)

## Components

### Buttons

**Primary Button**
```css
background: #FF6B35;
color: #FFFFFF;
padding: 12px 24px;
border-radius: 8px;
font-weight: 500;
transition: background 0.2s ease;
```
Hover: `background: #E55A2A;`

**Secondary Button**
```css
background: transparent;
color: #1A1A1A;
border: 1px solid #E5E0D8;
padding: 12px 24px;
border-radius: 8px;
```

### Cards

```css
background: #FFFFFF;
border: 1px solid #E5E0D8;
border-radius: 12px;
padding: 24px;
```

### Inputs

```css
background: #FFFFFF;
border: 1px solid #E5E0D8;
border-radius: 8px;
padding: 12px 16px;
```
Focus: `border-color: #FF6B35;`

## Iconography

- Style: Minimal, geometric
- Stroke width: 2px
- Corner radius: 4px
- Primary color: `#666666`
- Active color: `#FF6B35`

## Visual Motifs

### Starburst Icon
The signature Claude starburst shape (12-point radial) represents the brand and should use the bold orange color.

### Soft Shadows
```css
box-shadow: 0 2px 8px rgba(0, 0, 0, 0.04);
box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08); /* Elevated */
```

### Border Radius
- Small elements: `4px`
- Buttons, inputs: `8px`
- Cards: `12px`
- Large containers: `16px`

## Animation

```css
/* Standard transition */
transition: all 0.2s ease;

/* Subtle fade in */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to { opacity: 1; transform: translateY(0); }
}
```

## Accessibility

- Minimum contrast ratio: 4.5:1 for body text
- Focus states: `outline: 2px solid #FF6B35; outline-offset: 2px;`
- Touch target minimum: 44px × 44px

## Examples

### Hero Section
```
Warm beige background
Centered content
Large serif heading
Bold orange CTA button
```

### Navigation
```
Light cream background
Simple logo
Sparse links
Subtle border bottom
```

### Content Cards
```
White background
Soft border
Generous padding
Minimal shadow on hover
```
