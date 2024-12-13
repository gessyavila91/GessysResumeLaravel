# Documentation Changelog (Example)

This document records all changes made to the documentation.

## [Unreleased]

### Added
- Guide on adding new entities and attributes in `entity_and_attribute_changes_guide.md`.
- Detailed explanation on ERD updates in `erd_and_data_dictionary.md`.

### Changed
- Updated setup instructions in `implementation/setup_guide.md`.
- Enhanced user manual in `user_guide/user_manual.md`.

### Fixed
- Corrected formatting issues in `api_documentation.md`.

## [1.0.1] - YYYY-MM-DD

### Added
- Initial documentation for continuous integration in `deployment/continuous_integration.md`.

### Changed
- Revised non-functional requirements in `requirements/non_functional_requirements.md`.
- Expanded coding standards in `implementation/coding_standards.md`.

### Fixed
- Typos in `requirements/functional_requirements.md`.

---
### Protocol for Managing Changes

#### When Adding a New Functionality or Feature:

1. **Identify Documentation Impact**:
    - Determine which documentation files will be affected by the new functionality or feature.
    - This typically includes `README.md`, `introduction.md`, `requirements/functional_requirements.md`, `implementation/api_documentation.md`, `user_guide/user_manual.md`, and possibly `test_plan.md` and `test_cases.md`.

2. **Update Relevant Files**:
    - Update the impacted documentation files with the new information.
    - Ensure consistency and clarity across all documents.

3. **Log the Changes**:
    - Record the changes in `changelog.md` for the project.
    - Additionally, update `docs/changelog.md` to reflect the specific documentation changes.

4. **Review and Validate**:
    - Review the documentation changes to ensure accuracy and completeness.
    - Validate that all references and links are correct.

5. **Commit the Changes**:
    - Use conventional commit messages to document the changes made.
    - Example: `docs: update documentation for new feature XYZ`

```
git commit -m "docs: update and enhance documentation for new feature XYZ

- Added new feature description in `introduction.md`.
- Updated functional requirements in `requirements/functional_requirements.md`.
- Enhanced API documentation in `implementation/api_documentation.md`.
- Added user manual instructions for new feature in `user_guide/user_manual.md`.
- Logged changes in `docs/changelog.md`.

Co-authored-by: Copilot <copilot@microsoft.com>"
```
