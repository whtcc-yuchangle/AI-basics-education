## Style Prompt
Dark tech-education canvas inspired by code editors and developer tools. Clean, precise, modern. Deep charcoal backgrounds with cyan and amber accents create a focused coding environment feel. Motion is confident but restrained — crisp entrances, overlapping staggers, no fluff.

## Colors
- bg: #0a0e14 (canvas — deep charcoal, almost black)
- surface: #131820 (card backgrounds, secondary panels)
- surface2: #181e28 (hover states, tertiary panels)
- border: #1e2632 (dividers, hairline rules)
- text: #c8ccd4 (primary text — warm silver)
- text2: #8b919c (secondary text — muted gray)
- accent: #00d4ff (cyan — primary accent, highlights, CTAs)
- amber: #ffb74d (warm accent — emphasis, badges, warning)
- green: #00e676 (success, positive indicators)
- red: #ff5252 (errors, destructive)
- purple: #7c6ff7 (brand, tertiary accent)

## Typography
- Headline: DM Sans, weight 900, letter-spacing -0.02em
- Body: DM Sans, weight 350 (dark-background adjusted), line-height 1.5
- Code: Fira Code, weight 400 (no ligatures for Python), tabular-nums
- Data labels: DM Sans, weight 700, 18px+, tracking -0.01em

## Motion
- Entrances: stagger 80-120ms, overlap off previous element at 60%
- Easing: expo.out for headlines, power2.out for cards, sine.inOut for ambient
- Scene build phase: 0-30%, breathe: 30-70%, resolve: 70-100%
- Transitions: push slide (medium energy, 0.4s power2.inOut) — corporate/explainer feel

## What NOT to Do
- No gradient text (background-clip trick)
- No neon glow borders
- No centered-everything layouts — use split frames and anchors
- No identical card grids — vary sizes and positions
- No pure #000 or #fff — tint toward accent hue
- No exit animations (except final scene fadeout)
