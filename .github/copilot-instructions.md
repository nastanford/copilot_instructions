---
applyTo: "**/*"
---

# Global Coding Standards
- Ensure all content is 508 compliant for accessibility
- Use UTF-8 encoding for all files
- Use 2 spaces for indentation (no tabs)
- Use LF (Line Feed) for line endings
- Use meaningful and consistent naming conventions
- Add comments to explain complex logic and important decisions
- Maintain consistency across the entire project
- Use Bootstrap 5 for styling and layout
- Bootstrap should be linked in the header, no need to include in every file
- Use FontAwesome for icons, preferring duotone icons when available

# Database Conventions
- Use lowercase with underscores for table names (e.g., `user_accounts`, `order_items`)
- Use lowercase with underscores for column names (e.g., `first_name`, `created_at`)
- Use plural nouns for table names (e.g., `users`, `orders`)
- Use singular nouns for CFC names (e.g., `User`, `Order`)
- Cross-reference tables: `table1_table2` format (e.g., `users_roles`)
- Use `id` as the primary key column name for all tables
- Use `created_at` and `updated_at` for timestamp columns
- Use `created_by` and `updated_by` for user tracking (should reference user ID)

# Bootstrap Guidelines
- Use Bootstrap classes for layout and styling
- Avoid inline styles; use CSS classes instead
- Use Bootstrap grid system for responsive design
- Use Bootstrap components for consistent UI elements
- Customize via custom CSS file, not core Bootstrap files

# Form Standards
- Add FontAwesome icons for each form field
- Mark required fields with red asterisk (*)
- Add red "* - required" text at top of forms
- Include Bootstrap JavaScript for client-side validation
- Implement proper error messaging for required fields

# Code Style
- Use meaningful, descriptive names for all identifiers
- Keep code DRY (Don't Repeat Yourself)
- Use ternary operators where appropriate
- Align opening and closing braces/tags vertically
- Remove unused code, files, and dependencies regularly
- Use emojis in comments to enhance readability and visual appeal

# Best Practices
- Follow security best practices
- Ensure accessibility (a11y) compliance
- Ensure accessibility AA compliance
- Test code before committing
- Write clear commit messages
- Never commit secrets or credentials
- Maintain clear documentation
- Organize files and folders logically by feature or responsibility

# HTMX
- Offer suggestions for HTMX usage where applicable and as often as possible.
- Use `hx-target="##id"` to escape CSS hash symbols inside `<cfoutput>` blocks
- Use `hx-boost="true"` on forms to enhance user experience
- Consider using `hx-swap="outerHTML"` for replacing entire elements
- Use `hx-indicator` to show loading states for better UX
- Use `hx-include` to include additional data in requests when necessary
- Use `hx-confirm` for actions that require user confirmation

# Sessions 
- Use `session.message` to store a message after insert, update or delete.
- Display `session.message` on the next page load and then clear it. 

# SEO
- Add meta description tags to all pages for better search engine optimization
- Use meaningful titles for all pages
- Use semantic HTML5 elements for better SEO and accessibility
