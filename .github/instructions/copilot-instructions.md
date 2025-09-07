---
applyTo: "**/*"
---

# Global Coding Standards
- Use bootstrap 4 or 5 for styling and layout.
- Bootstrap link normally found in the header so no need to include it in every file.
- Use FontAwesome for icons.
- Add a enter in the code after the icon this is not a <br> but just a enter to help the readability.
- Prefer duotone icons when possible.

# ColdFusion Application Unit Testing
If you are building a ColdFusion application and using unit testing, ensure that the `/testbox` folder is present in the `wwwroot` directory. This is required for TestBox-based unit tests to run correctly in a standard ColdFusion setup.

# Additional Best Practices
- Write clear, concise comments for complex logic and important decisions.
- Use meaningful, descriptive names for files, variables, functions, and classes.
- Avoid committing secrets, credentials, or sensitive data to version control.
- Keep code DRY (Don’t Repeat Yourself); use reusable components and functions.
- Organize files and folders logically by feature or responsibility.
- Write and maintain a `README.md` with setup, usage, and contribution guidelines.
- Use version control (e.g., Git) and write clear commit messages.
- Ensure accessibility (a11y) best practices in UI code.
- Test code before committing; include automated tests where possible.
- Remove unused code, files, and dependencies regularly.
- Follow security best practices for the relevant language/framework.

## Editor Settings
- Use 2 spaces per tab for all files. This is enforced via the `.editorconfig` file in the project root.
