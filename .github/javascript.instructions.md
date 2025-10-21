---
applyTo: "**/*.js"
---

# JavaScript Best Practices Guide

This guide outlines JavaScript-specific best practices for clean, maintainable, and accessible code.

## 🧩 Modern JavaScript Standards

- Use **ES6+** features (const/let, arrow functions, template literals, destructuring)
- Prefer `const` for variables that don't change, `let` for variables that do
- Avoid `var` - use `const` and `let` instead
- Use arrow functions for short, simple functions
- Use template literals for string interpolation: `Hello ${name}`

## 🎯 Variable and Function Naming

- Use **camelCase** for variables and functions (e.g., `getUserData`, `applicationId`)
- Use **PascalCase** for classes and constructors (e.g., `UserService`, `ApplicationManager`)
- Use **UPPER_SNAKE_CASE** for constants (e.g., `API_ENDPOINT`, `MAX_RETRIES`)
- Use descriptive names that explain purpose (e.g., `isUserLoggedIn` not `flag`)

## 🔧 Function Best Practices

- Keep functions small and focused on single responsibility
- Use descriptive function names that explain what they do
- Return early to avoid deep nesting
- Use default parameters instead of checking for undefined
- Prefer pure functions when possible (no side effects)

```javascript
// Good
function calculateTotalPrice(items, taxRate = 0.08) {
  if (!items || items.length === 0) return 0;
  
  const subtotal = items.reduce((sum, item) => sum + item.price, 0);
  return subtotal * (1 + taxRate);
}
```

## 🌐 DOM Manipulation

- Use modern DOM methods: `querySelector`, `querySelectorAll`
- Cache DOM elements when accessed multiple times
- Use event delegation for dynamic content
- Always check if elements exist before manipulating them
- Use `addEventListener` instead of inline event handlers

```javascript
// Good
const submitButton = document.querySelector('#submitBtn');
if (submitButton) {
  submitButton.addEventListener('click', handleSubmit);
}
```

## 📡 AJAX and Fetch API

- Use `fetch()` API instead of older XMLHttpRequest
- Always handle both success and error cases
- Use async/await for cleaner asynchronous code
- Include proper error handling and user feedback

```javascript
// Good
async function fetchUserData(userId) {
  try {
    const response = await fetch(`/api/users/${userId}`);
    
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    
    const userData = await response.json();
    return userData;
  } catch (error) {
    console.error('Failed to fetch user data:', error);
    throw error;
  }
}
```

## 🎭 Event Handling

- Use event delegation for dynamic content
- Prevent default behavior when needed
- Clean up event listeners to prevent memory leaks
- Use descriptive event handler names

```javascript
// Good - Event delegation
document.addEventListener('click', function(e) {
  if (e.target.matches('.delete-btn')) {
    e.preventDefault();
    handleDelete(e.target.dataset.id);
  }
});
```

## 🔒 Security Best Practices

- Validate and sanitize all user input
- Use textContent instead of innerHTML when possible
- Escape HTML content when using innerHTML
- Implement proper CSRF protection
- Never expose sensitive data in client-side code

## 🎨 UI/UX Best Practices

- Provide visual feedback for user actions (loading states, success/error messages)
- Use debouncing for search inputs and frequent events
- Implement proper form validation with clear error messages
- Ensure keyboard navigation works properly
- Follow WCAG accessibility guidelines

```javascript
// Good - Debounced search
function debounce(func, wait) {
  let timeout;
  return function executedFunction(...args) {
    const later = () => {
      clearTimeout(timeout);
      func(...args);
    };
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
}

const searchInput = document.querySelector('#search');
const debouncedSearch = debounce(performSearch, 300);
searchInput.addEventListener('input', debouncedSearch);
```

## 🧪 Error Handling

- Use try/catch blocks for asynchronous operations
- Log errors with meaningful messages
- Provide user-friendly error messages
- Fail gracefully - don't break the entire application

## 📊 Performance Considerations

- Minimize DOM queries and manipulations
- Use event delegation instead of multiple event listeners
- Debounce/throttle expensive operations
- Lazy load content when appropriate
- Avoid memory leaks by cleaning up references

## 🎛️ HTMX Integration (if applicable)

- Use HTMX attributes for simple interactions
- Combine with vanilla JavaScript for complex logic
- Handle HTMX events properly (`htmx:afterRequest`, etc.)
- Provide fallbacks for when JavaScript is disabled

```javascript
// Good - HTMX event handling
document.body.addEventListener('htmx:afterRequest', function(evt) {
  if (evt.detail.successful) {
    showSuccessMessage('Operation completed successfully');
  } else {
    showErrorMessage('An error occurred. Please try again.');
  }
});
```
