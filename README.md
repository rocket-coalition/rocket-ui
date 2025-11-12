# 🚀 RocketUI

**CSS that thinks. You describe intent. It handles everything.**

```html
<!-- Before: 40 hours of CSS hell -->
<div class="flex items-center justify-between px-4 py-2 bg-white dark:bg-gray-900 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-200 border border-gray-200 dark:border-gray-700 md:px-6 lg:px-8 xl:rounded-xl">

<!-- After: Zero CSS. Just intent. -->
<body data-theme="ocean" data-density="normal">
  <div class="card">
```

**Change theme. Entire site re-styles. 0.2 seconds.**

---

## The 10-Second Proof

### 🎨 Three numbers. Infinite themes.

```css
/* Change these 3 values */
--L-primary: 0.68;   /* lightness */
--C-primary: 0.17;   /* chroma */
--H-primary: 250deg; /* hue */

/* Get 9 shades automatically */
/* primary-50 through primary-900 */
/* Math-generated. Perfect contrast. */
```

### 📱 Mobile? Already done.

```html
<!-- iOS notch: auto-handled -->
<!-- Touch targets: auto-sized (44px) -->
<!-- Dark mode: auto-detected -->
<!-- Fluid type: auto-scales -->
<!-- Zero config. Zero manual work. -->
```

### 🎯 Describe feeling. Get design.

```html
<!-- Calm professional docs site -->
<body data-theme="mint" data-density="spacious">

<!-- Energetic SaaS landing -->
<body data-theme="sunset" data-density="normal">

<!-- Dense data dashboard -->
<body data-theme="rocket-dark" data-density="compact">
```

**13 themes. 3 densities. 3 layouts. = 117 combinations. Pick one.**

---

## Your First 5 Minutes

### Step 1: Add to your Tailwind config (15 seconds)

```css
/* input.css */
@import 'tailwindcss';
@import 'daisyui';
@import './rocket-ui.css';
```

### Step 2: Pick your vibe (10 seconds)

```html
<body data-theme="ocean" data-density="normal">
```

### Step 3: Build structure (2 minutes)

```html
<div class="layout-site-frame layout-landing-page">
  <header class="layout-header sticky" role="banner">
    <nav>Logo | Docs | Pricing</nav>
  </header>
  
  <main class="layout-main" role="main">
    <section id="hero">
      <h1>Your headline</h1>
      <button class="btn btn-primary">Start Free</button>
    </section>
  </main>
  
  <footer class="layout-footer" role="contentinfo">
    © 2025 Your Company
  </footer>
</div>
```

### Step 4: Ship it (done)

**Professional site. Mobile-optimized. Accessible. Zero custom CSS.**

---

## The Three Layouts

### 📄 Single Page — Docs, articles, readability

```html
<div class="layout-site-frame layout-single-page">
  <!-- Narrow column. Large type. -->
  <!-- Perfect for reading. -->
</div>
```

### 🚀 Landing Page — Marketing, conversion, full-width

```html
<div class="layout-site-frame layout-landing-page">
  <!-- Hero sections. Sticky nav. -->
  <!-- Built to convert. -->
</div>
```

### 📊 Multi-Page — Apps, dashboards, sidebar nav

```html
<div class="layout-site-frame layout-multi-page">
  <header class="layout-header">Top nav</header>
  <aside class="layout-sidebar">Side nav</aside>
  <main class="layout-main">Content</main>
</div>
```

---

## The Power: Real Examples

### Example 1: Change entire vibe (one attribute)

```html
<!-- Professional bank site -->
<body data-theme="ocean">

<!-- Playful startup -->
<body data-theme="candy">

<!-- High-tech SaaS -->
<body data-theme="cyberpunk">
```

**Same HTML. Different personality. 10 seconds.**

---

### Example 2: Spacing control (one attribute)

```html
<!-- Dashboard: tight, focused -->
<body data-density="compact">

<!-- Marketing: generous, breathable -->
<body data-density="spacious">
```

**Same content. Different energy.**

---

### Example 3: Dark mode (auto or manual)

```html
<!-- Auto: respects OS preference -->
<body>

<!-- Force dark -->
<body data-theme="rocket-dark">

<!-- Force light -->
<body data-theme="rocket">
```

**Zero JavaScript. Pure CSS.**

---

### Example 4: Create custom theme (2 minutes)

```css
[data-theme="mybrand"] {
  --H-primary: 340deg;  /* hot pink */
  --C-primary: 0.24;    /* vibrant */
  --L-primary: 0.70;    /* balanced */
}
```

```html
<body data-theme="mybrand">
```

**9 color shades generated. Contrast guaranteed. Done.**

---

## What You Get (Automatically)

### ✅ Mobile Perfection
- iOS safe areas (notch handled)
- 44px touch targets (Apple guidelines)
- Fluid typography (no breakpoints)
- Momentum scrolling (smooth iOS)
- Auto-compact spacing (<768px)

### ✅ Accessibility Baked In
- WCAG 2.1 AA compliant
- Keyboard navigation
- Screen reader support
- Focus indicators (keyboard only)
- Semantic HTML structure

### ✅ Performance
- 11KB gzipped
- CSS-only (zero JavaScript)
- ~150ms compile time
- Modern browsers (OKLCH support)

### ✅ Developer Experience
- 13 curated themes
- 3 layout patterns
- 3 density modes
- DaisyUI components integrated
- Copy-paste examples

---

## The Components (via DaisyUI)

```html
<!-- Buttons: just work -->
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>

<!-- Cards: theme-aware -->
<div class="card">
  <div class="card-body">
    <h2 class="card-title">Title</h2>
    <p>Content adapts to theme automatically.</p>
  </div>
</div>

<!-- Alerts: color-coded -->
<div class="alert alert-info">Info message</div>
<div class="alert alert-success">Success!</div>
<div class="alert alert-warning">Warning</div>
<div class="alert alert-error">Error</div>

<!-- Forms: styled by default -->
<input type="text" class="input" placeholder="Just works">
<select class="select">
  <option>Dropdown</option>
</select>
```

**50+ components. All theme-aware. Zero configuration.**

---

## The Themes

```
🟦 rocket        — Default purple. Professional.
🌑 rocket-dark   — Dark mode. Easy on eyes.
🌲 forest        — Green/teal. Calm and earthy.
🌊 ocean         — Deep blue. Trust and stability.
🌅 sunset        — Orange/pink. Warm and energetic.
💡 neon          — Hot pink/cyan. Bold and loud.
🤖 cyberpunk     — Purple/yellow. High-tech future.
🌿 mint          — Fresh green. Clean and modern.
💜 lavender      — Soft purple. Gentle and creative.
⚫ monochrome    — Pure B&W. Minimal and focused.
📼 retro         — Brown/orange. 1980s nostalgia.
🌌 cosmic        — Deep purple. Mysterious space.
🍬 candy         — Bright pink. Playful and fun.
```

**Pick one. Or create your own in 2 minutes.**

---

## Real-World Usage

### Docs Site (30 seconds)

```html
<body data-theme="mint" data-density="spacious">
  <div class="layout-site-frame layout-single-page">
    <main class="layout-main">
      <article class="prose">
        <!-- Your markdown content -->
      </article>
    </main>
  </div>
</body>
```

**Readable. Calm. Professional. Done.**

---

### SaaS Landing (2 minutes)

```html
<body data-theme="ocean" data-density="normal">
  <div class="layout-site-frame layout-landing-page">
    <header class="layout-header sticky">
      <nav>Logo | Features | Pricing | Login</nav>
    </header>
    
    <main class="layout-main">
      <section id="hero">
        <h1>Stop Fighting CSS</h1>
        <p>Start shipping products.</p>
        <button class="btn btn-primary btn-lg">Start Free Trial</button>
      </section>
      
      <section id="features">
        <div class="grid grid-cols-3 gap-8">
          <!-- Feature cards -->
        </div>
      </section>
    </main>
  </div>
</body>
```

**Converts. Scales. Ships.**

---

### Dashboard (3 minutes)

```html
<body data-theme="rocket-dark" data-density="compact">
  <div class="layout-site-frame layout-multi-page">
    <header class="layout-header">
      <span>Dashboard</span>
      <div class="user-menu">User</div>
    </header>
    
    <aside class="layout-sidebar">
      <nav>
        <a href="#dashboard">Dashboard</a>
        <a href="#analytics">Analytics</a>
        <a href="#settings">Settings</a>
      </nav>
    </aside>
    
    <main class="layout-main">
      <!-- Data tables, charts, widgets -->
    </main>
  </div>
</body>
```

**Focused. Dense. Professional.**

---

## The Secret: OKLCH Color Math

### Traditional approach (pain)

```css
/* Manual color picking */
--primary-50: #eff6ff;
--primary-100: #dbeafe;
/* ... 7 more manual definitions */
--primary-900: #1e3a8a;

/* Hope contrast ratios work */
/* Hope dark mode doesn't break it */
/* Hope accessibility passes */
```

### RocketUI approach (smart)

```css
/* 3 inputs */
--L-primary: 0.68;
--C-primary: 0.17;
--H-primary: 250deg;

/* 9 shades auto-generated */
/* Math-based color scaling */
/* Guaranteed contrast ratios */
/* Dark mode: just remap semantics */
```

**Change 1 hue. Entire theme regenerates. 0.2 seconds.**

---

## Advanced: Custom Theme

```css
/* Your brand colors */
[data-theme="acme"] {
  /* Primary: Brand blue */
  --L-primary: 0.65;
  --C-primary: 0.22;
  --H-primary: 210deg;
  
  /* Secondary: Brand orange */
  --L-secondary: 0.68;
  --C-secondary: 0.24;
  --H-secondary: 35deg;
}
```

```html
<body data-theme="acme">
  <!-- Entire site uses your brand -->
  <!-- Buttons, cards, alerts: all themed -->
  <!-- Dark mode variant: auto-compatible -->
</body>
```

**Two minutes. Production-ready theme.**

---

## Complete Production Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My App</title>
  <link rel="stylesheet" href="output.css">
</head>
<body data-theme="ocean" data-density="normal">
  
  <div class="layout-site-frame layout-landing-page">
    
    <!-- Header: Sticky navigation -->
    <header class="layout-header sticky" role="banner">
      <nav class="navbar bg-base-100">
        <div class="flex-1">
          <a class="btn btn-ghost text-xl">RocketUI</a>
        </div>
        <div class="flex-none">
          <ul class="menu menu-horizontal px-1">
            <li><a href="#features">Features</a></li>
            <li><a href="#pricing">Pricing</a></li>
            <li><a class="btn btn-primary">Sign Up</a></li>
          </ul>
        </div>
      </nav>
    </header>
    
    <!-- Main: Content sections -->
    <main class="layout-main" role="main">
      
      <!-- Hero Section -->
      <section id="hero" class="hero min-h-screen">
        <div class="hero-content text-center">
          <div class="max-w-md">
            <h1 class="text-5xl font-bold">Stop Fighting CSS</h1>
            <p class="py-6">Change 3 numbers. Get entire design system. Ship in 5 minutes.</p>
            <button class="btn btn-primary btn-lg">Get Started</button>
            <button class="btn btn-outline btn-lg">View Docs</button>
          </div>
        </div>
      </section>
      
      <!-- Features Section -->
      <section id="features" class="py-20">
        <div class="container mx-auto px-4">
          <h2 class="text-3xl font-bold text-center mb-12">Everything You Need</h2>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            
            <div class="card bg-base-200">
              <div class="card-body">
                <h3 class="card-title">🎨 13 Themes</h3>
                <p>Professional, dark, cyberpunk, ocean, candy. Switch instantly.</p>
              </div>
            </div>
            
            <div class="card bg-base-200">
              <div class="card-body">
                <h3 class="card-title">📱 Mobile First</h3>
                <p>iOS safe areas, 44px touches, fluid type. Zero config.</p>
              </div>
            </div>
            
            <div class="card bg-base-200">
              <div class="card-body">
                <h3 class="card-title">♿ Accessible</h3>
                <p>WCAG 2.1 AA. Keyboard nav. Screen readers. Built-in.</p>
              </div>
            </div>
            
          </div>
        </div>
      </section>
      
      <!-- CTA Section -->
      <section id="pricing" class="py-20 bg-base-200">
        <div class="container mx-auto px-4 text-center">
          <h2 class="text-3xl font-bold mb-6">Start Building Today</h2>
          <p class="text-xl mb-8">Copy rocket-ui.css. Add to Tailwind. Ship.</p>
          <div class="flex gap-4 justify-center">
            <button class="btn btn-primary btn-lg">Download CSS</button>
            <button class="btn btn-secondary btn-lg">View Examples</button>
          </div>
        </div>
      </section>
      
    </main>
    
    <!-- Footer -->
    <footer class="layout-footer" role="contentinfo">
      <div class="footer footer-center p-10">
        <div>
          <p class="font-bold">RocketUI Design System</p>
          <p>CSS that thinks. Built with Tailwind + DaisyUI + OKLCH math.</p>
        </div>
        <div>
          <p>MIT License · Rocket Coalition</p>
        </div>
      </div>
    </footer>
    
  </div>
  
</body>
</html>
```

**Requirements:**
- Tailwind CSS 4.x
- DaisyUI 5.x  
- rocket-ui.css (this system)

**That's it. Production-ready landing page. Zero custom CSS.**

---

## Philosophy

**Traditional CSS:** Specify HOW (pixels, colors, breakpoints)  
**RocketUI:** Specify WHY (intent, feeling, purpose)

**Traditional:** `padding: 24px` (arbitrary)  
**RocketUI:** `data-density="spacious"` (intentional)

**Traditional:** 600 color definitions (manual)  
**RocketUI:** 15 LCH inputs (generative)

**Traditional:** 40 hours per project (repetitive)  
**RocketUI:** 5 minutes per project (systematic)

---

**CSS that thinks. Finally.**
