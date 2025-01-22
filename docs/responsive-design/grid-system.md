# Grid System

## Desktop
- Grid Columns: 12
- Gutter Width: 1.5rem (15px)

## Tablet
- Grid Columns: 8
- Gutter Width: 1rem (10px)

## Mobile
- Grid Columns: 4
- Gutter Width: 0.5rem (5px)

# Grid System

| Screen Size | Grid Columns | Gutter Width (Gap) |
|-------------|--------------|--------------------|
| Desktop     | 12           | 1.5rem (15px)      |
| Tablet      | 8            | 1rem (10px)        |
| Mobile      | 4            | 0.5rem (5px)       |

### Example CSS:
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 1.5rem;
}

@media (max-width: 768px) {
  .grid-container {
    grid-template-columns: repeat(8, 1fr);
    gap: 1rem;
  }
}

@media (max-width: 480px) {
  .grid-container {
    grid-template-columns: repeat(4, 1fr);
    gap: 0.5rem;
  }
}