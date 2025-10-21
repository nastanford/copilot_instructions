---
applyTo: "**/*.cfm"
---

# ColdFusion
- Current only using ColdFusion 2025 make sure to specify that in any relevant documentation and make sure to use features specific to that version where applicable.

# ColdFusion CFM Usage Guide

- This guide outlines best practices for writing `.cfm` files that interact with CFC services in a clean and maintainable way.

## 🧼 Controller Logic

- Keep `.cfm` files focused on **input/output** and **view rendering**
- Avoid placing business logic directly in `.cfm` files

## 🧩 Service Instantiation

Use clear and consistent variable names when instantiating services:

```coldfusion
oApplication = new models.applications.service();
result = oApplication.getById(applicationId);
```

## 🧪 Code Review Checklist

- [ ] Are you only calling the Service layer?
- [ ] Is the service variable named after the domain (oUser, oApplication)?
- [ ] Are you avoiding direct calls to DAO or Bean?
- [ ] Is the logic clean and readable?
- [ ] Are you handling errors gracefully?

## 🧱 Example Usage

```coldfusion
<cfset oUser = new models.users.service()>
<cfset userData = oUser.getById(userId)>
<cfoutput>#userData.name#</cfoutput>
```

## 🧠 Tips

- Use consistent naming across all `.cfm` files
- Keep logic modular and reusable
- Document service methods clearly for easier integration

# ColdFusion-Specific Naming Conventions

- Use **snake_case** for ColdFusion variable and function names (e.g., `my_variable`, `get_user_data`)
- Use **PascalCase** for component (CFC) names (e.g., `UserService`, `OrderProcessor`)
- Use **lowercase with hyphens** for CFM file names (e.g., `user-profile.cfm`, `order-summary.cfm`)

# ColdFusion-Specific Standards

- Use CFScript where possible for cleaner syntax
- Avoid using deprecated tags and functions
- Use `cfqueryparam` to prevent SQL injection
- Escape CSS hash symbols inside `<cfoutput>` blocks using `##`
- When using HTMX inside `<cfoutput>` blocks, escape hash symbols (#) by using double hashes (##) to prevent unintended variable interpolation
- If you are in a HTMX target file then make sure the top line is: `<cfsetting showDebugOutput = "false">`

# ColdFusion Unit Testing

If you are building a ColdFusion application and using unit testing, ensure that the `/testbox` folder is present in the `wwwroot` directory. This is required for TestBox-based unit tests to run correctly in a standard ColdFusion setup.

# CFM-Specific Best Practices

- Use `Application.cfc` for application settings and request handling
- Organize code into reusable CFCs (components) for maintainability
- Use `cftry`/`cfcatch` for error handling and logging
- Prefer `cfinclude` for shared templates, but avoid circular includes

