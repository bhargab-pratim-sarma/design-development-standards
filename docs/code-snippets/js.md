#### **`docs/code-snippets/js.md`**
```markdown
# JavaScript Code Snippets

## Fetching Data from an API
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));