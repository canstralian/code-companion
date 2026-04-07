```markdown
# code-companion Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and workflows used in the `code-companion` repository, a Python project built with the Flask framework. You'll learn about the project's coding conventions, dependency update workflows, and testing patterns, with practical examples and ready-to-use commands for automation.

## Coding Conventions

### File Naming
- **Style:** snake_case
- **Example:**  
  ```
  user_service.py
  utils/helpers.py
  ```

### Import Style
- **Style:** Relative imports
- **Example:**
  ```python
  from .models import User
  from ..utils import parse_config
  ```

### Export Style
- **Style:** Named exports (explicitly listing exported symbols)
- **Example:**
  ```python
  __all__ = ['UserService', 'get_user_by_id']
  ```

### Commit Patterns
- **Type:** Freeform messages, sometimes with prefixes
- **Average Length:** ~38 characters

## Workflows

### multi-directory-pip-dependency-bump
**Trigger:** When dependencies need to be updated across several subprojects or modules at once.  
**Command:** `/bump-dependencies pip`

1. **Identify directories** containing `requirements.txt` or `pyproject.toml` files.
2. **Update dependency versions** for specified packages in each file.
   - For example, update `Flask==2.2.3` to `Flask==2.3.0` in all relevant files.
3. **Commit all updated files together** with a message listing updated packages and versions.
   - Example commit message:  
     ```
     Bump Flask to 2.3.0 and requests to 2.28.2 in all modules
     ```

**Files Involved:**
- `**/requirements.txt`
- `**/pyproject.toml`

**Frequency:** ~1-2x/month

**Example:**
```bash
# In each subdirectory:
pip install --upgrade -r requirements.txt
# Or manually edit requirements.txt/pyproject.toml, then:
git add requirements.txt pyproject.toml
git commit -m "Bump Flask to 2.3.0 in all modules"
```

## Testing Patterns

- **Framework:** Unknown (not explicitly detected)
- **File Pattern:** `*.test.*`
  - Example: `user_service.test.py`, `utils/test_helpers.py`
- **Typical Test File Example:**
  ```python
  def test_user_creation():
      user = create_user('alice')
      assert user.name == 'alice'
  ```

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /bump-dependencies pip | Update pip dependencies across all relevant directories      |
```
