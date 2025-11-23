# Benjamin - Green Healthcare Design System

**Platform:** Web (Desktop/Modal)
**Mode:** Light
**Design Philosophy:** Clean, professional medical interface with green healthcare identity inspired by FONS system

---

## Color Palette

### Primary Color
- **Base Green:** `#5CB85C` / `#4CAF50`
- **Hover Green:** `#45A049` (darker on hover)
- **Active Green:** `#3D8B40` (pressed state)
- **Usage:** Primary buttons, active states, headers, brand accents

### Surface Colors
- **Background Base:** `#FFFFFF` (Pure White)
- **Background Alt:** `#F5F5F5` (Light Gray - for contrast areas)
- **Surface Card:** `#FFFFFF` with `border: 1px solid #E0E0E0`
- **Elevated Surface:** `#FFFFFF` with `box-shadow: 0 2px 8px rgba(0,0,0,0.08)`

### Text Colors
- **Primary Text:** `#212121` (Dark Charcoal)
- **Secondary Text:** `#616161` (Medium Gray)
- **Tertiary/Hint:** `#9E9E9E` (Light Gray)
- **On Primary (White text on green):** `#FFFFFF`

### Semantic Colors
- **Success:** `#4CAF50` (Green - same as primary)
- **Warning:** `#FFC107` (Amber)
- **Error:** `#F44336` (Red)
- **Info:** `#2196F3` (Blue)

### Border Colors
- **Default:** `#E0E0E0` (Light Gray)
- **Focus:** `#5CB85C` (Primary Green)
- **Divider:** `#EEEEEE` (Very Light Gray)

### Interactive States
- **Hover:** Darken by 10% + `box-shadow: 0 2px 6px rgba(0,0,0,0.12)`
- **Active/Pressed:** Darken by 20%
- **Disabled:** `opacity: 0.4` + `cursor: not-allowed`
- **Focus Ring:** `0 0 0 2px rgba(92, 184, 92, 0.3)`

---

## Typography

### Font Family
- **Primary:** `-apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Helvetica Neue', Arial, sans-serif`
- **Monospace:** `'SF Mono', 'Consolas', 'Monaco', monospace`

### Type Scale

| Element | Size | Weight | Line Height | Usage |
|---------|------|--------|-------------|-------|
| **H1** | 24px | 600 (SemiBold) | 32px | Page title, modal header |
| **H2** | 20px | 600 (SemiBold) | 28px | Section headers |
| **H3** | 18px | 600 (SemiBold) | 26px | Card titles |
| **Body** | 14px | 400 (Regular) | 20px | Main content |
| **Body Small** | 13px | 400 (Regular) | 18px | Secondary content |
| **Caption** | 12px | 400 (Regular) | 16px | Labels, metadata |
| **Button** | 14px | 500 (Medium) | 20px | Button text |
| **Label** | 13px | 500 (Medium) | 18px | Input labels |

### Text Treatments
- **Links:** Color `#5CB85C`, underline on hover
- **Emphasis:** `font-weight: 600`, color stays same
- **Code/Inline:** `background: #F5F5F5`, `padding: 2px 6px`, `border-radius: 3px`

---

## Spacing & Layout

### Spacing Scale (8px base unit)
- **4px:** Micro spacing (icon-text gap)
- **8px:** Tight spacing (inline elements)
- **12px:** Compact spacing (small padding)
- **16px:** Default spacing (standard padding/margin)
- **20px:** Medium spacing
- **24px:** Large spacing (section gaps)
- **32px:** Extra large spacing

### Grid & Containers
- **Modal Container:** Flexible width (min 800px, max 1400px) × auto height
- **Content Max Width:** 100% minus padding
- **Two-Column Split:** 50% / 50% with 16px gap
- **Sidebar Width:** 280px (navigation menu)

---

## Border Radius

| Element | Radius | Usage |
|---------|--------|-------|
| **None** | `0px` | Default for most containers |
| **Small** | `3px` | Badges, tags, inline code |
| **Medium** | `4px` | Buttons, inputs |
| **Large** | `6px` | Cards (if used) |
| **Rounded Corners (Header)** | `8px 8px 0 0` | Top corners of modal |

**Note:** Design uses minimal border radius - mostly sharp corners for professional medical feel.

---

## Shadows & Elevation

### Shadow Levels
- **Level 1 (Subtle):** `0 1px 3px rgba(0,0,0,0.06)`
  *Usage:* Subtle elevation, input focus
- **Level 2 (Default):** `0 2px 8px rgba(0,0,0,0.08)`
  *Usage:* Cards, dropdowns
- **Level 3 (Modal):** `0 4px 16px rgba(0,0,0,0.12)`
  *Usage:* Modal overlays

**Note:** Design prefers flat surfaces with borders over heavy shadows.

---

## Components

### Buttons

#### Primary Button (Green)
```css
background: #5CB85C;
color: #FFFFFF;
padding: 10px 20px;
border-radius: 4px;
border: none;
font-size: 14px;
font-weight: 500;
cursor: pointer;
transition: background 0.2s ease;

/* Hover */
background: #45A049;

/* Active */
background: #3D8B40;

/* Disabled */
background: #A5D6A7;
opacity: 0.6;
cursor: not-allowed;
```

#### Secondary Button (Gray)
```css
background: #F5F5F5;
color: #616161;
padding: 10px 20px;
border-radius: 4px;
border: 1px solid #E0E0E0;

/* Hover */
background: #EEEEEE;
border-color: #BDBDBD;
```

#### Ghost Button (Transparent)
```css
background: transparent;
color: #616161;
padding: 10px 20px;
border-radius: 4px;
border: none;

/* Hover */
background: #F5F5F5;
color: #212121;
```

### Header Bar (Green)

```css
background: #5CB85C;
color: #FFFFFF;
padding: 12px 16px;
border-radius: 8px 8px 0 0; /* Rounded top corners */
display: flex;
justify-content: space-between;
align-items: center;

/* Title */
font-size: 18px;
font-weight: 600;
display: flex;
align-items: center;
gap: 8px;

/* Icons */
color: #FFFFFF;
font-size: 20px;
cursor: pointer;
opacity: 0.9;

/* Icon Hover */
opacity: 1;
```

### Inputs & Textareas

```css
background: #FFFFFF;
border: 1px solid #E0E0E0;
border-radius: 4px;
padding: 10px 12px;
font-size: 14px;
color: #212121;
transition: border-color 0.2s ease;

/* Focus */
border-color: #5CB85C;
outline: none;
box-shadow: 0 0 0 2px rgba(92, 184, 92, 0.2);

/* Placeholder */
color: #9E9E9E;

/* Disabled */
background: #F5F5F5;
color: #9E9E9E;
cursor: not-allowed;
```

### Toolbar (Icon Buttons)

```css
/* Container */
background: #FFFFFF;
border-bottom: 1px solid #E0E0E0;
padding: 8px 12px;
display: flex;
gap: 4px;

/* Icon Button */
width: 32px;
height: 32px;
display: flex;
align-items: center;
justify-content: center;
border-radius: 4px;
border: none;
background: transparent;
color: #616161;
cursor: pointer;
transition: background 0.15s ease;

/* Hover */
background: #F5F5F5;
color: #212121;

/* Active */
background: #E0E0E0;
color: #5CB85C;
```

### Navigation Menu (Sidebar)

```css
/* Container */
background: #FFFFFF;
border-right: 1px solid #E0E0E0;
width: 280px;
padding: 12px 0;

/* Search Input */
margin: 0 12px 12px;
padding: 8px 12px;
background: #F5F5F5;
border: 1px solid #E0E0E0;
border-radius: 4px;

/* Menu Item */
padding: 12px 16px;
display: flex;
align-items: center;
gap: 12px;
color: #616161;
font-size: 14px;
cursor: pointer;
transition: background 0.15s ease;
border-left: 3px solid transparent;

/* Menu Item Hover */
background: #F5F5F5;

/* Menu Item Active */
background: rgba(92, 184, 92, 0.1);
color: #5CB85C;
border-left-color: #5CB85C;
font-weight: 500;

/* Icon */
font-size: 20px;
width: 24px;
text-align: center;
```

### Modal Container

```css
background: #FFFFFF;
border-radius: 8px;
box-shadow: 0 4px 16px rgba(0,0,0,0.12);
overflow: hidden;
max-width: 1200px;
width: 90vw;
max-height: 90vh;
display: flex;
flex-direction: column;
```

### Cards (if needed)

```css
background: #FFFFFF;
border: 1px solid #E0E0E0;
border-radius: 6px;
padding: 16px;
transition: box-shadow 0.2s ease;

/* Hover */
box-shadow: 0 2px 8px rgba(0,0,0,0.08);
```

### Dividers

```css
/* Horizontal */
border-bottom: 1px solid #EEEEEE;
margin: 16px 0;

/* Vertical */
border-right: 1px solid #EEEEEE;
```

### Badges

```css
background: #E8F5E9; /* Light green */
color: #2E7D32; /* Dark green */
padding: 4px 8px;
border-radius: 3px;
font-size: 12px;
font-weight: 500;
```

### Status Indicators

```css
/* Online/Success */
background: #4CAF50;
color: #FFFFFF;

/* Warning */
background: #FFC107;
color: #FFFFFF;

/* Error/Offline */
background: #F44336;
color: #FFFFFF;

/* Info */
background: #2196F3;
color: #FFFFFF;
```

---

## Layout Patterns

### Two-Column Editor Layout

```
┌─────────────────────────────────────────────────────────┐
│ [Green Header Bar]                                      │
├─────────────────────────────────────────────────────────┤
│ [Toolbar with Icons]                                    │
├──────────────────────────┬──────────────────────────────┤
│                          │                              │
│  Původní text            │  Návrh AI                    │
│  (Left Panel)            │  (Right Panel)               │
│                          │                              │
│  [Text Input Area]       │  [AI Output Area]            │
│                          │                              │
├──────────────────────────┴──────────────────────────────┤
│ Poslední změna: [User, Time]                            │
│ [Action Buttons]                                        │
└─────────────────────────────────────────────────────────┘
```

### Sidebar Navigation Layout

```
┌────────┬──────────────────────────────────────────────┐
│        │ [Content Area]                               │
│ Menu   │                                              │
│ Items  │                                              │
│        │                                              │
│ [Icon] │                                              │
│ Label  │                                              │
│        │                                              │
└────────┴──────────────────────────────────────────────┘
```

---

## Interaction & Animation

### Transition Timing
- **Fast:** `0.15s` (hover feedback)
- **Default:** `0.2s` (most interactions)
- **Slow:** `0.3s` (modals)
- **Easing:** `ease` or `cubic-bezier(0.4, 0, 0.2, 1)`

### Micro-interactions
- **Button Click:** Slight darken on active
- **Menu Item Select:** Background color change
- **Focus:** Border color change + shadow
- **Loading:** Simple spinner or progress bar

---

## Accessibility

### Focus States
- **Keyboard Focus:** `box-shadow: 0 0 0 2px rgba(92, 184, 92, 0.3);`
- Use `:focus-visible` for keyboard-only focus indicators

### Color Contrast
- **Primary Text on White:** 16:1 (AAA)
- **Secondary Text on White:** 7:1 (AA)
- **White Text on Green:** 4.6:1 (AA)

### Interactive Target Size
- **Minimum:** 32×32px for icon buttons
- **Buttons:** At least 36px height
- **Touch Targets:** 44×44px minimum

---

## Design Principles

1. **Professional & Clinical:** Clean, minimal design suitable for medical environment
2. **Green Healthcare Identity:** Consistent use of green (#5CB85C) for trust and healthcare association
3. **Flat Design:** Minimal shadows, reliance on borders and spacing for hierarchy
4. **Clear Hierarchy:** Strong typographic scale and spacing for content organization
5. **Efficiency:** Dense information display suitable for power users (doctors)
6. **Accessibility:** High contrast, clear focus states, keyboard navigation

---

**Design Rationale:**
This design system is inspired by the FONS medical system interface, prioritizing clinical professionalism, information density, and workflow efficiency. The green color palette establishes healthcare credibility while maintaining a clean, modern aesthetic. Flat surfaces with clear borders ensure content remains the focus, while consistent spacing and typography create predictable, learnable patterns for time-pressed medical professionals.
