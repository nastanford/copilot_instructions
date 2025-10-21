---
applyTo: "**/*.cfc"
---

# ColdFusion CFC Development Guide

This guide outlines best practices for structuring and writing ColdFusion Component (CFC) files using a modular, domain-driven approach.

## 📁 Folder Structure

Organize each domain model in its own folder:
```
/models/{domain}/
  bean.cfc
  dao.cfc
  service.cfc
```

Example:
```
/models/applications/
  bean.cfc
  dao.cfc
  service.cfc
```

## 📛 CFC-Specific Naming Conventions

- Use **singular** names for files: `bean.cfc`, `dao.cfc`, `service.cfc`
- Folder name represents the domain (e.g., `applications`, `users`)
- Avoid generic names like `model.cfc` unless it's a base class
- Use **snake_case** for ColdFusion variable and function names (e.g., `my_variable`, `get_user_data`)
- Use **PascalCase** for component (CFC) names (e.g., `UserService`, `OrderProcessor`)

## 🧩 Component Roles

- **Bean**: Represents the data structure (like a DTO)
- **DAO**: Handles direct database access
- **Service**: Contains business logic and acts as the public interface

## 🔐 Access Control

- Only the **Service** should be called externally
- DAO and Bean should be used **privately** within the Service

## 🧪 Code Review Checklist

- [ ] Are methods named consistently (`getById`, `getAll`, `save`, `delete`)?
- [ ] Is the DAO only accessed through the Service?
- [ ] Are components scoped correctly (`public`, `private`)?
- [ ] Is the folder structure domain-driven?
- [ ] Are you avoiding logic in the Bean?

## 🧱 Example Service Usage

```coldfusion
component {
  property name="dao" inject="models.applications.dao";

  public any function getById(required numeric id) {
    return dao.getById(id);
  }
}
```

# ColdFusion CFC-Specific Standards

- Use CFScript where possible for cleaner syntax
- Avoid using deprecated tags and functions
- Use `cfqueryparam` to prevent SQL injection in DAO methods
- Escape CSS hash symbols inside `<cfoutput>` blocks using `##`

# CFC-Specific Best Practices

- Use `this` scope for component properties and methods when appropriate
- Document all functions with purpose, parameters, and return values (use Javadoc or similar style)
- Use access modifiers (`public`, `private`, `package`, `remote`) for functions and variables
- Prefer dependency injection for component collaboration
- Avoid business logic in setters/getters; keep them simple
- Validate and sanitize all input parameters in public/remote methods
- Use `cftry`/`cfcatch` for error handling within methods as needed
- Group related methods logically within the component
- Avoid using `cfcomponent` attributes that are deprecated or unnecessary
