#### **`docs/font-theory/typography-styles.md`**
```markdown
# Typography Styles

## Heading Hierarchy
- H1: Bold, 3rem (30px)
- H2: Semi-bold, 2.5rem (25px)
- H3: Medium, 2rem (20px)

## Body Text
- Font Size: 1.6rem (16px)
- Line Height: 1.6

### Example CSS:
```css
h1 {
  font-size: 3rem;
  font-weight: bold;
}

body {
  font-size: 1.6rem;
  line-height: 1.6;
}

# Line Heights and Text Gaps

| Element       | Line Height | Text Gap (Margin) | Tablet/Mobile Adjustments       |
|---------------|-------------|-------------------|---------------------------------|
| H1            | 1.3         | 1.5rem (15px)     | Reduce margin to 1rem (10px).   |
| H2            | 1.4         | 1.25rem (12.5px)  | Keep same or reduce slightly.   |
| Body Text     | 1.6         | 1rem (10px)       | Keep line height consistent.    |
| Button Text   | 1.2         | 0.75rem (7.5px)   | Keep minimal gap.               |