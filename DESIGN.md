# Project Design System (DESIGN.md)

This document establishes the design principles, color palettes, typography, and styling tokens for the premium doctor and clinic website.

## Color Palette

The project uses a clinical, modern, and trustworthy color scheme consisting of whites, medical blues, and light mint greens.

| Color Role | Light Mode Value | Dark Mode Value | Tailwind Class Mapping |
| :--- | :--- | :--- | :--- |
| **Primary Blue (Trust)** | HSL(217, 91%, 56%) | HSL(217, 91%, 65%) | `text-blue-600` / `bg-blue-600` |
| **Deep Blue (Navy)** | HSL(222, 47%, 11%) | HSL(222, 47%, 95%) | `text-slate-900` / `bg-slate-900` |
| **Accent Green (Health)** | HSL(152, 60%, 45%) | HSL(152, 60%, 55%) | `text-emerald-500` / `bg-emerald-500` |
| **Light BG** | HSL(210, 40%, 98%) | HSL(222, 47%, 8%) | `bg-slate-50` / `dark:bg-slate-950` |
| **Card / Section BG** | HSL(0, 0%, 100%) | HSL(222, 47%, 12%) | `bg-white` / `dark:bg-slate-900` |
| **Soft Muted Text** | HSL(215, 16%, 47%) | HSL(215, 20%, 65%) | `text-slate-500` / `dark:text-slate-400` |

---

## Typography

We prefetch two Google Fonts for optimal load time and typography hierarchy:
1. **Outfit**: Used for titles, headings, and CTA buttons to present a modern, friendly, yet professional look.
2. **Inter**: Used for paragraphs, body text, form labels, and detailed listings to ensure optimal reading accessibility.

### Font Styles

- **Main Heading (H1)**: `font-family: 'Outfit', sans-serif; font-weight: 700; text-wrap: balance; line-height: 1.15;`
- **Sub-Headings (H2, H3)**: `font-family: 'Outfit', sans-serif; font-weight: 600; text-wrap: pretty;`
- **Body Text**: `font-family: 'Inter', sans-serif; font-weight: 400; line-height: 1.6;`
- **CTAs & Labels**: `font-family: 'Outfit', sans-serif; font-weight: 500; letter-spacing: 0.02em;`

---

## UI Components & Accents

### Glassmorphism Specs
For sticky elements, interactive cards, and overlays:
- **Background**: `rgba(255, 255, 255, 0.7)` / `dark:rgba(15, 23, 42, 0.7)`
- **Blur**: `backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px);`
- **Border**: `1px solid rgba(255, 255, 255, 0.2)` / `dark:1px solid rgba(255, 255, 255, 0.05)`
- **Shadow**: `box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.04);`

### Shadows and Borders
- **Standard Card Shadow**: Soft and deep, e.g., `shadow-xl shadow-slate-100/40 dark:shadow-none`
- **Border Radius**: Rounded shapes for a modern, friendly feel. `rounded-2xl` for cards, `rounded-3xl` or `rounded-full` for CTA buttons.
- **Accents**: Subtle light-green gradient overlays and thin borders to draw attention.

---

## Animations and Micro-Interactions

### Keyframe Animations

1. **Float**: A gentle up-and-down oscillation for medical background icons.
   ```css
   @keyframes float {
     0%, 100% { transform: translateY(0); }
     50% { transform: translateY(-10px); }
   }
   ```
2. **Fade-In-Up**: Smooth vertical reveal for text and grids upon entering the screen.
   ```css
   @keyframes fadeInUp {
     from { opacity: 0; transform: translateY(20px); }
     to { opacity: 1; transform: translateY(0); }
   }
   ```
3. **Pulse-Glow**: A soft glow pulsating behind key buttons or sections to encourage action.

### Smooth Transitions
- Strictly avoid `transition: all`.
- List specific animatable properties: `transition-colors`, `transition-transform`, `transition-opacity` with cubic-bezier timing (`transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.4s cubic-bezier(0.16, 1, 0.3, 1);`).
