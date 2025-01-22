#### **`docs/color-theory/color-contrast.md`**
```markdown
# Color Contrast

## Best Practices
- Ensure a contrast ratio of at least **4.5:1** for text and background colors.
- Use tools like [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) to verify contrast.

### Example:
```css
body {
  background-color: var(--white);
  color: var(--dark-gray);
}

.button {
  background-color: var(--primary);
  color: var(--white);
}