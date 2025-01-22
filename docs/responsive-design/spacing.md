
---

#### **`docs/responsive-design/spacing.md`**
```markdown
# Spacing

## Global Spacing System
| Element          | Desktop       | Tablet        | Mobile          |
|------------------|---------------|---------------|-----------------|
| Section Padding  | 3rem (30px)   | 2rem (20px)   | 1.5rem (15px)   |
| Element Padding  | 1.5rem (15px) | 1rem (10px)   | 0.75rem (7.5px) |
| Element Margin   | 1.5rem (15px) | 1rem (10px)   | 0.75rem (7.5px) |

# Container Sizes
| Screen Size | Container Width | Padding (Gaps)   |
|-------------|-----------------|------------------|
| Desktop     | 1200px          | 2rem (20px)      |
| Tablet      | 960px           | 1.5rem (15px)    |
| Mobile      | 100% (fluid)    | 1rem (10px)      |

Best Practice: Use a combination of px for max-width and % or rem for fluid responsiveness:
css
.container {
  max-width: 1200px; /* Fixed for desktop */
  width: 100%; /* Flexible for smaller screens */
  padding: 2rem; /* Consistent spacing */
  margin: 0 auto;
}

# Icon Sizes and Gaps

| Icon Type    | Desktop Size   | Tablet Size    | Mobile Size    | Gap/Spacing     |
|--------------|----------------|----------------|----------------|-----------------|
| Small Icons  | 16px–20px      | 14px–18px      | 12px–16px      | 0.5rem (5px)    |
| Medium Icons | 24px–32px      | 20px–28px      | 18px–24px      | 1rem (10px)     |
| Large Icons  | 40px–48px      | 36px–40px      | 32px–36px      | 1.5rem (15px)   |

### Example CSS:
```css
.section {
  padding: 3rem 1.5rem;
}

.element {
  padding: 1.5rem;
  margin: 1.5rem;
}

# Default Gap Recommendations

1. **Use `rem` for gaps** to maintain scalability.
2. **Define a global scale for gaps** in your CSS variables (`:root`).
3. **Apply the gaps consistently** for grids, flexboxes, margins, and paddings.
4. **Use media queries** to adjust gaps for smaller screens.

### Example CSS:
```css
:root {
  --gap-xs: 0.5rem; /* 8px */
  --gap-sm: 1rem;   /* 16px */
  --gap-md: 1.5rem; /* 24px */
  --gap-lg: 2rem;   /* 32px */
  --gap-xl: 3rem;   /* 48px */
}

.grid-container {
  display: grid;
  gap: var(--gap-md); /* Consistent gaps between items */
}

@media (max-width: 768px) {
  :root {
    --gap-xs: 0.25rem; /* 4px */
    --gap-sm: 0.5rem;  /* 8px */
    --gap-md: 1rem;    /* 16px */
    --gap-lg: 1.5rem;  /* 24px */
    --gap-xl: 2rem;    /* 32px */
  }
}

# Recommendation

## For Global Containers
- Use `%` for **width**, `rem` for **padding**, and optionally `vw/vh` for full-screen elements.
- Combine with **max-width** to prevent containers from stretching too wide on large screens.
- Keep a **centered layout** using `margin: 0 auto`.

### Example CSS:
```css
.container {
  width: 90%;
  max-width: 1200px; /* Prevents stretching on large screens */
  padding: 2rem;     /* Consistent padding with rem */
  margin: 0 auto;    /* Centers the container */
}

.fullscreen-section {
  width: 100vw;
  height: 100vh;     /* Fullscreen element */
}

# Using Container Size in px – Is it Good or Bad?

Using container size in `px` can have pros and cons, depending on your website's needs. Here's a breakdown:

## Why Using `px` Can Be Good
1. **Predictability**:
   - Pixel values provide absolute control, ensuring the container size remains fixed regardless of font size or user settings.
2. **Design Consistency**:
   - For desktop designs, fixed widths (e.g., `1200px`) can align well with traditional grid systems.

## Why Using `px` Can Be Bad
1. **Lack of Responsiveness**:
   - Fixed `px` sizes do not adapt to screen size changes, making the design less flexible for tablets and mobiles.
2. **Accessibility Issues**:
   - If users increase their browser's font size or zoom level, a `px`-based container might not scale properly.
3. **Modern Standards Favor Flexibility**:
   - Industry standards lean towards relative units like `rem`, `%`, or `vw`, which adjust dynamically to various screen sizes.

## Best Practice
- Use a combination of **relative and fixed units** for optimal flexibility and consistency:
  - **Desktop**: Use `max-width` in `px` for the container's upper limit (e.g., `1200px`).
  - **Responsive Sizes**: Use `%` or `rem` for smaller screen adjustments.

### Example CSS:
```css
.container {
  max-width: 1200px; /* Fixed for desktop */
  width: 100%;       /* Flexible for smaller screens */
  padding: 2rem;     /* Consistent spacing */
  margin: 0 auto;    /* Centered layout */
}

# Should You Use vw/vh for Containers?

Using `vw` (viewport width) and `vh` (viewport height) for containers depends on your design needs. Here's when and why to use (or not use) these units for containers:

---

## When to Avoid `vw/vh` for Containers

### For Width (`vw`):
1. **Lack of Consistency**:
   - Using `100vw` can cause unwanted horizontal scrolling due to the scrollbar width.
2. **Fixed Layouts**:
   - `vw` isn't ideal if you want your content to align with grid systems or have consistent padding.

#### Best Alternative:
Use `max-width` in `px` for a fixed limit and `%` for responsiveness.

```css
.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 1rem;
}

# For Height (vh):
  Not Suitable for Content-Heavy Pages:

  Using 100vh can make the container height unreasonably large or small, especially on mobile devices where the browser toolbar can distort the viewport height.

Best Alternative:
  Allow the container height to adapt naturally or use min-height with vh only when absolutely necessary (e.g., for hero sections or fullscreen layouts).

  .hero {
  min-height: 100vh; /* Fullscreen hero section */
  }

# When to Use vw/vh for Containers
  Fullscreen Sections or Backgrounds:
    Use 100vw or 100vh for sections that should span the entire viewport, like hero banners or fullscreen modals.
    .fullscreen-container {
  width: 100vw;
  height: 100vh;
    }

# Fluid, Edge-to-Edge Layouts:
  For designs where the container needs to span the full viewport width (e.g., a carousel), vw is helpful.

Interactive Elements:
  Use vh for dynamically adjusting elements like popups or scrollable overlays.