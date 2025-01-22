
---

#### **`docs/responsive-design/typography.md`**
```markdown
# Typography

# Global Text Sizes

| Element       | Desktop           | Tablet            | Mobile            |
|---------------|-------------------|-------------------|-------------------|
| H1            | 3rem (30px)       | 2.5rem (25px)     | 2rem (20px)       |
| H2            | 2.5rem (25px)     | 2rem (20px)       | 1.75rem (17.5px)  |
| H3            | 2rem (20px)       | 1.75rem (17.5px)  | 1.5rem (15px)     |
| H4            | 1.75rem (17.5px)  | 1.5rem (15px)     | 1.25rem (12.5px)  |
| Body Text     | 1.6rem (16px)     | 1.5rem (15px)     | 1.4rem (14px)     |
| Subheading    | 1.5rem (15px)     | 1.4rem (14px)     | 1.25rem (12.5px)  |
| Button Text   | 1.25rem (12.5px)  | 1.2rem (12px)     | 1rem (10px)       |
| Small Text    | 1rem (10px)       | 0.9rem (9px)      | 0.8rem (8px)      |

# Line Heights and Text Gaps

| Element       | Line Height | Text Gap (Margin) | Tablet/Mobile Adjustments       |
|---------------|-------------|-------------------|---------------------------------|
| H1            | 1.3         | 1.5rem (15px)     | Reduce margin to 1rem (10px).   |
| H2            | 1.4         | 1.25rem (12.5px)  | Keep same or reduce slightly.   |
| Body Text     | 1.6         | 1rem (10px)       | Keep line height consistent.    |
| Button Text   | 1.2         | 0.75rem (7.5px)   | Keep minimal gap.               |

# Button Sizes and Padding

| Screen Size | Padding Y (Vertical) | Padding X (Horizontal) | Font Size       |
|-------------|----------------------|------------------------|-----------------|
| Desktop     | 0.75rem (7.5px)      | 1.5rem (15px)          | 1.25rem (12.5px)|
| Tablet      | 0.6rem (6px)         | 1.25rem (12.5px)       | 1.2rem (12px)   |
| Mobile      | 0.5rem (5px)         | 1rem (10px)            | 1rem (10px)     |

.button {
  padding: 0.75rem 1.5rem; /* Y = 0.75rem, X = 1.5rem */
  font-size: 1.25rem;
}

# Button Padding Y and X – What Does It Mean?

Button padding **Y (Vertical)** and **X (Horizontal)** refer to the spacing inside a button, measured along the vertical and horizontal axes, respectively.

## Explanation:
1. **Padding Y (Vertical)**:
   - Space **above and below** the text inside the button.
2. **Padding X (Horizontal)**:
   - Space **to the left and right** of the text inside the button.

.button {
  padding: 0.75rem 1.5rem; /* Desktop */
}

@media (max-width: 768px) {
  .button {
    padding: 0.6rem 1.25rem; /* Tablet */
  }
}

@media (max-width: 480px) {
  .button {
    padding: 0.5rem 1rem; /* Mobile */
  }
}

### Example CSS:
```css
.button {
  padding: 0.75rem 1.5rem; /* Y = 0.75rem, X = 1.5rem */
}

### Line Heights
- Body Text: 1.6
- Headings: 1.3

### Example CSS:
```css
h1 { font-size: 3rem; line-height: 1.3; }
h2 { font-size: 2.5rem; line-height: 1.3; }
body { font-size: 1.6rem; line-height: 1.6; }

# Comparison of Units

## `px` (Pixels)
- **Fixed size**, does not scale with user preferences or browser settings.
- **Avoid using it globally**.

## `em`
- Relative to the **parent element**.
- Can lead to **compounding issues** where nested elements scale unexpectedly.

## `rem`
- Relative to the **root element**, offering consistent scaling across your website.

## `%`
- Often used for **container widths**, but not ideal for text.

## `vw/vh` (Viewport Width/Height)
- Good for **very large or dynamic headlines** but not ideal for body text.