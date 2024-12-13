# Entity and Attribute Changes Guide

This document provides a detailed guide on how How to Create a New Entity or Add/Change an Attribute and handle changes when adding new attributes or entities to the data dictionary. It outlines the steps to follow, the related documentation files that need to be updated, and the order of changes for ensuring accuracy and precision.

## How to Create a New Entity or Add/Change an Attribute

### Creating a New Entity

1. **Define the Entity**:
    - Determine the entity name and its attributes.
    - Write a brief description of what the entity represents.

2. **Update Data Dictionary**:
    - Add a new row to the data dictionary table in `erd_and_data_dictionary.md`.

   **Example**:
```markdown
   | Entity Name          | Attributes                                             | Description                                  |
   |----------------------|--------------------------------------------------------|----------------------------------------------|
   | NewEntity            | id, attribute1, attribute2, ..., attributeN            | Description of the new entity                |
```

3. **Update ERD Diagram**:
    - Add the new entity to the ERD diagram section of `erd_and_data_dictionary.md`.

**Example**:

mermaid
```
erDiagram
    NewEntity {
        int id PK
        string attribute1
        string attribute2
        ...
        string attributeN
    }
    # Add relationships as needed
    NewEntity ||--o{ ExistingEntity: has
```

### Adding/Changing an Attribute on an Existing Entity

1. **Identify the Entity**:
    - Find the entity in the data dictionary and ERD diagram.

2. **Update Data Dictionary**:
    - Modify the attributes in the data dictionary table for the entity.

**Example**:

```
| Entity Name          | Attributes                                             | Description                                  |
|----------------------|--------------------------------------------------------|----------------------------------------------|
| ExistingEntity       | id, existing_attribute1, new_attribute, ..., existing_attributeN | Description of the existing entity           |
```

3. **Update ERD Diagram**:
    - Modify the entity attributes in the ERD diagram.

**Example**:

```
erDiagram
    ExistingEntity {
        int id PK
        string existing_attribute1
        string new_attribute
        ...
        string existing_attributeN
    }
    # Update relationships as needed
    ExistingEntity_1 ||--o{ ExistingEntity_2: has
```

## Steps to Add New Attributes or Entities

1. **Update the Data Dictionary** (`design/data_dictionary.md`)

2. **Update the API Documentation** (`implementation/api_documentation.md`)

3. **Update the Functional Requirements** (`requirements/functional_requirements.md`)

4. **Update the Non-Functional Requirements** (`requirements/non_functional_requirements.md`)

5. **Update the Test Plan** (`testing/test_plan.md`)

6. **Update the Test Cases** (`testing/test_cases.md`)

7. **Update the User Manual** (`user_guide/user_manual.md`)

8. **Update the FAQ** (`user_guide/faq.md`)

9. **Review the Deployment Guide** (`deployment/deployment_guide.md`)

10. **Update Continuous Integration Configurations** (`deployment/continuous_integration.md`)
## Steps to Add New Attributes or Entities

### Step 1: Update the Data Dictionary
- **File**: `design/data_dictionary.md`
- **Action**: Add the new attributes or entities with detailed descriptions.

### Step 2: Update the API Documentation
- **File**: `implementation/api_documentation.md`
- **Action**: Update the API endpoints to include the new attributes or entities. Ensure request and response formats are accurately described.

### Step 3: Update the Functional Requirements
- **File**: `requirements/functional_requirements.md`
- **Action**: Ensure that the functional requirements reflect the changes. Add any new functionality related to the new attributes or entities.

### Step 4: Update the Non-Functional Requirements
- **File**: `requirements/non_functional_requirements.md`
- **Action**: Review and update any non-functional requirements that might be impacted by the changes, such as performance or scalability considerations.

### Step 5: Update the Test Plan
- **File**: `testing/test_plan.md`
- **Action**: Add new test scenarios to cover the new attributes or entities.

### Step 6: Update the Test Cases
- **File**: `testing/test_cases.md`
- **Action**: Create or update test cases to validate the new attributes or entities.

### Step 7: Update the User Manual
- **File**: `user_guide/user_manual.md`
- **Action**: Include instructions on how users can interact with the new attributes or entities in the application.

### Step 8: Update the FAQ
- **File**: `user_guide/faq.md`
- **Action**: Add or update FAQ entries that might be relevant to the new attributes or entities.

### Step 9: Review the Deployment Guide
- **File**: `deployment/deployment_guide.md`
- **Action**: Ensure any new configurations or dependencies related to the new attributes or entities are documented.

### Step 10: Update Continuous Integration Configurations
- **File**: `deployment/continuous_integration.md`
- **Action**: Review and update CI configurations to include tests for the new attributes or entities.

## Order of Changes for Accuracy and Precision

1. **Update the Data Dictionary** (`design/data_dictionary.md`)
2. **Update the API Documentation** (`implementation/api_documentation.md`)
3. **Update the Functional Requirements** (`requirements/functional_requirements.md`)
4. **Update the Non-Functional Requirements** (`requirements/non_functional_requirements.md`)
5. **Update the Test Plan** (`testing/test_plan.md`)
6. **Update the Test Cases** (`testing/test_cases.md`)
7. **Update the User Manual** (`user_guide/user_manual.md`)
8. **Update the FAQ** (`user_guide/faq.md`)
9. **Review the Deployment Guide** (`deployment/deployment_guide.md`)
10. **Update Continuous Integration Configurations** (`deployment/continuous_integration.md`)
