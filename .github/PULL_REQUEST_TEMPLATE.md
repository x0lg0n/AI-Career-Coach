name: Pull Request
description: Create a pull request to contribute to this project
title: ""
labels: []
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        Thanks for contributing to AI Career Coach! 🚀
        
        Please fill out this template to help us review your pull request.

  - type: dropdown
    id: pr-type
    attributes:
      label: Type of Change
      description: What type of change does this PR introduce?
      options:
        - Bug fix (non-breaking change which fixes an issue)
        - New feature (non-breaking change which adds functionality)
        - Breaking change (fix or feature that would cause existing functionality to not work as expected)
        - Documentation update
        - Performance improvement
        - Code refactoring
        - Dependency update
        - Other
    validations:
      required: true

  - type: textarea
    id: description
    attributes:
      label: Description
      description: Please describe the changes you've made
      placeholder: |
        - What does this PR do?
        - Why was this change needed?
        - How does it solve the problem?
    validations:
      required: true

  - type: textarea
    id: related-issues
    attributes:
      label: Related Issues
      description: Link any related issues
      placeholder: |
        Fixes #123
        Closes #456
        Related to #789

  - type: textarea
    id: testing
    attributes:
      label: Testing
      description: Describe how you tested your changes
      placeholder: |
        - [ ] Unit tests added/updated
        - [ ] Integration tests added/updated
        - [ ] Manual testing completed
        - [ ] All existing tests pass
    validations:
      required: true

  - type: textarea
    id: screenshots
    attributes:
      label: Screenshots
      description: If applicable, add screenshots of your changes
      placeholder: Drag and drop or paste screenshots here

  - type: checkboxes
    id: checklist
    attributes:
      label: Checklist
      description: Please check all that apply
      options:
        - label: My code follows the style guidelines of this project
          required: true
        - label: I have performed a self-review of my own code
          required: true
        - label: I have commented my code, particularly in hard-to-understand areas
          required: false
        - label: I have made corresponding changes to the documentation
          required: false
        - label: My changes generate no new warnings
          required: true
        - label: I have added tests that prove my fix is effective or that my feature works
          required: false
        - label: New and existing unit tests pass locally with my changes
          required: true

  - type: textarea
    id: additional-notes
    attributes:
      label: Additional Notes
      description: Any additional information that reviewers should know
      placeholder: Add any other context about the pull request here