# The Three-Variable Revelation
**How Generative Math Unlocked Infinite Themes**

---


*the insight that changed everything*

---

I had this moment around 3am.

Couldn't sleep. Frustrated with color systems. AGAIN.

Every project: manually pick colors. Manually generate shades. Manually test contrast. Manually maintain light AND dark versions.

**There had to be a better way.**

Then it hit me.

---

## The Old Way (Insanity)

Traditional color system setup:

```css
/* Primary color family - all manual */
--primary-50: #eff6ff;
--primary-100: #dbeafe;
--primary-200: #bfdbfe;
--primary-300: #93c5fd;
--primary-400: #60a5fa;
--primary-500: #3b82f6;   /* base */
--primary-600: #2563eb;
--primary-700: #1d4ed8;
--primary-800: #1e40af;
--primary-900: #1e3a8a;
```

Now multiply by:
- 5 color families (primary, secondary, success, warning, error)
- 2 themes (light + dark)
- 3 projects per year
- 20 years

**= 600 color definitions I've manually created**

Each time:
1. Pick a base color
2. Use online tool to generate shades
3. Copy hex codes
4. Test contrast ratios
5. Adjust until WCAG compliant
6. Realize dark mode breaks it
7. Start over

**This is not engineering. This is torture.**

---

## The Question

At 3am, brain fried, I asked myself:

**"What if I could describe a color with just 3 numbers and generate everything else?"**

Not hex codes. Not RGB. Not HSL (which lies about brightness).

What if there was a color space that ACTUALLY represents how humans perceive color?

---

## Enter OKLCH

I found OKLCH color space.

**Perceptually uniform.** Unlike HSL/HSV/RGB where "lightness" is broken.

Three components:
- **L** = Lightness (0-1, actual perceived brightness)
- **C** = Chroma (0-0.4, how colorful vs gray)
- **H** = Hue (0-360deg, position on color wheel)

The breakthrough:

**Change L by 0.1, brightness changes by EXACTLY 10% to human eyes.**

HSL lies: `hsl(240, 50%, 50%)` and `hsl(60, 50%, 50%)` have SAME lightness value but look completely different brightness.

OKLCH tells truth: `oklch(0.5 0.2 240deg)` and `oklch(0.5 0.2 60deg)` have SAME perceived brightness.

---

## The Insight

If OKLCH is perceptually uniform...

**I can generate color scales with MATH.**

Not by eyeballing. Not with tools. Pure algorithmic generation.

```css
/* Base: 3 inputs */
--L-primary: 0.68;   /* lightness */
--C-primary: 0.17;   /* chroma (saturation) */
--H-primary: 250deg; /* hue (color) */

/* Generate lighter shades: increase L, decrease C */
--primary-50: oklch(
  calc(var(--L-primary) + 0.30)   /* much lighter */
  calc(var(--C-primary) * 0.50)   /* less saturated */
  var(--H-primary)                 /* same hue */
);

/* Generate darker shades: decrease L, maintain C */
--primary-900: oklch(
  calc(var(--L-primary) - 0.24)   /* much darker */
  calc(var(--C-primary) * 0.85)   /* slightly less saturated */
  var(--H-primary)                 /* same hue */
);
```

**Change 1 number. 9 shades regenerate automatically.**

---

## Testing The Theory

I wrote the generator system at 4am.

Then tested:

### Test 1: Change hue
```css
--H-primary: 250deg; /* purple */
```
→ Entire site: purple theme. Instant.

```css
--H-primary: 150deg; /* green */
```
→ Entire site: green theme. Instant.

**SAME LIGHTNESS. SAME CONTRAST. Different color.**

### Test 2: Change chroma
```css
--C-primary: 0.05; /* muted */
```
→ Professional, subtle, calm

```css
--C-primary: 0.25; /* vibrant */
```
→ Bold, energetic, loud

**SAME HUE. SAME BRIGHTNESS. Different intensity.**

### Test 3: Dark mode
I DON'T change the color definitions.

I just remap SEMANTIC tokens:
```css
/* Light mode */
--bg: white;
--fg: var(--primary-900); /* dark text */

/* Dark mode */
--bg: var(--gray-900);
--fg: var(--primary-100); /* light text */
```

**Color ramps stay same. Meaning changes.**

---

## The Math

Here's the actual formula I landed on:

```css
/* Lighter shades (50-400) */
L_new = L_base + offset   /* increase brightness */
C_new = C_base * factor   /* decrease saturation (pastel effect) */

/* Base shade (500) */
L_new = L_base            /* unchanged */
C_new = C_base            /* unchanged */

/* Darker shades (600-900) */
L_new = L_base - offset   /* decrease brightness */
C_new = C_base * factor   /* maintain saturation */
```

Specific values after testing:
- 50: L+0.30, C×0.50
- 100: L+0.25, C×0.60
- 200: L+0.18, C×0.80
- 300: L+0.10, C×0.90
- 400: L+0.05, C×1.00
- 500: base (no change)
- 600: L-0.06, C×1.00
- 700: L-0.12, C×0.95
- 800: L-0.18, C×0.90
- 900: L-0.24, C×0.85

**These numbers are NOT arbitrary.**

Tested across:
- 50+ hue values
- Light and dark modes
- WCAG contrast ratios
- Multiple device screens

**They just work.**

---

## The Revelation

After I got this working, I realized:

**I haven't "picked colors" in weeks.**

I just:
1. Set L, C, H (3 numbers)
2. System generates 9 shades
3. Contrast automatically works
4. Dark mode automatically works
5. Every variant automatically works

**From 600 manual color definitions to 15 inputs (3 per color family × 5 families).**

**97.5% reduction in manual work.**

---

## Why This Changes Everything

### Old workflow:
"I need a new theme for the marketing site"

1. Designer picks colors (2 hours)
2. Designer generates shades (1 hour)
3. Designer tests contrast (1 hour)
4. Designer creates dark mode version (2 hours)
5. Developer implements (3 hours)
6. Test on devices (2 hours)
7. Fix issues (3 hours)

**Total: 14 hours**

### New workflow:
"I need a new theme for the marketing site"

1. Pick hue: `--H-primary: 160deg` (mint green)
2. Done.

**Total: 30 seconds**

---

## What Becomes Possible

Once you have generative colors:

### Infinite themes
```css
[data-theme="forest"] { --H-primary: 150deg; }
[data-theme="ocean"]  { --H-primary: 210deg; }
[data-theme="sunset"] { --H-primary: 30deg; }
[data-theme="neon"]   { --H-primary: 330deg; --C-primary: 0.30; }
```

**13 themes = 39 variable changes. Not 600 definitions.**

### Dynamic theming
```javascript
// User picks their vibe
userVibe = "energetic";
if (userVibe === "energetic") {
  document.body.style.setProperty('--C-primary', '0.25'); // high chroma
} else if (userVibe === "calm") {
  document.body.style.setProperty('--C-primary', '0.12'); // low chroma
}
```

**Change personality without rebuilding CSS.**

### Brand variations
```css
/* Client A: Purple brand */
--H-primary: 280deg;

/* Client B: Teal brand */
--H-primary: 180deg;

/* SAME CSS FILE. Different brand. */
```

### Accessibility auto-fixes
```css
/* If contrast fails, auto-darken */
--primary-700: oklch(
  clamp(0, calc(var(--L-primary) - 0.12), 1)  /* never negative */
  calc(var(--C-primary) * 0.95)
  var(--H-primary)
);
```

**Math ensures constraints. No manual testing.**

---

## The Meta-Lesson

For 20 years I was MANUALLY doing what MATH should do.

Picking shades by eye → **Should be algorithmic**  
Testing contrast ratios → **Should be baked into generator**  
Creating dark mode variants → **Should be semantic remapping**  
Maintaining consistency → **Should be impossible to break**

**The insight wasn't "use OKLCH."**

**The insight was "stop doing manual work that math can guarantee."**

---

## Why This Works For My Brain

I'm an engineer. I think in systems.

**I can't eyeball whether #3B82F6 and #DBEAFE are properly related.**

**But I CAN design a system where: "lighter shade = base + 0.25L, × 0.60C"**

THAT makes sense to me.

One algorithm. Infinite applications.

Change inputs, outputs regenerate correctly.

**This is engineering.**

Not "does this feel balanced?" (designer brain)  
But "does this math maintain perceptual uniformity?" (engineer brain)

---

## The Future Expansion

This is just colors.

**What else can be generative?**

### Typography scale:
```css
--text-base: 1rem;
--text-scale: 1.25; /* golden ratio */

/* Generate sizes */
--text-sm: calc(var(--text-base) / var(--text-scale));
--text-lg: calc(var(--text-base) * var(--text-scale));
--text-xl: calc(var(--text-base) * var(--text-scale) * var(--text-scale));
```

**One ratio. Infinite sizes. Perfect harmony.**

### Spacing scale:
```css
--space-base: 0.25rem; /* 4px */
--space-factor: 2;

/* Generate scale */
--space-1: var(--space-base);
--space-2: calc(var(--space-base) * var(--space-factor));
--space-4: calc(var(--space-base) * var(--space-factor) * var(--space-factor));
```

**One base unit. Perfect rhythm.**

### Shadow depth:
```css
--shadow-base-opacity: 0.15;
--shadow-base-blur: 4px;

/* Generate depths */
--shadow-sm: 0 1px 2px rgba(0,0,0,calc(var(--shadow-base-opacity) * 0.5));
--shadow-lg: 0 10px 20px rgba(0,0,0,calc(var(--shadow-base-opacity) * 1.5));
```

**One opacity value. Consistent depth perception.**

---

## The Core Truth

**Design systems should be generative, not documentary.**

Don't document 600 colors.  
Generate them from 15 inputs.

Don't document 47 spacing values.  
Generate them from 1 base unit.

Don't document 30 shadow variations.  
Generate them from 1 opacity curve.

**Humans set constraints. Math ensures consistency.**

---

## The 3am Realization

That night, staring at color systems, I finally understood:

**I'd been maintaining OUTPUTS when I should've been designing INPUTS.**

600 color definitions = maintaining outputs  
15 LCH inputs = designing inputs

**This changes everything.**

Not just for colors. For EVERYTHING.

If you can describe the SYSTEM mathematically...  
You never touch the outputs again.

---

**— rocketman**  
*The three-variable revolution*
