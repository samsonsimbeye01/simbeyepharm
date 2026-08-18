name: 🐛 Bug Report
description: Report a bug or issue with the platform
title: "[BUG] "
labels: ["bug", "triage"]
assignees: ["samsonsimbeye01"]

body:
  - type: markdown
    attributes:
      value: |
        ## 🐛 Bug Report
        Thank you for reporting a bug! Please provide detailed information to help us fix it quickly.

  - type: checkboxes
    attributes:
      label: "Prerequisites"
      description: "Please check the following before submitting:"
      options:
        - label: "I have searched existing issues and this is not a duplicate"
          required: true
        - label: "I have read the documentation"
          required: false
        - label: "I am using the latest version"
          required: false

  - type: textarea
    attributes:
      label: "Description"
      description: "Clear description of the bug"
      placeholder: "Describe what went wrong..."
      required: true

  - type: textarea
    attributes:
      label: "Steps to Reproduce"
      description: "Step-by-step instructions to reproduce the issue"
      placeholder: |
        1. Navigate to...
        2. Click on...
        3. See error...
      required: true

  - type: textarea
    attributes:
      label: "Expected Behavior"
      description: "What should happen instead?"
      placeholder: "The page should display correctly..."
      required: true

  - type: textarea
    attributes:
      label: "Actual Behavior"
      description: "What actually happens?"
      placeholder: "The page shows an error..."
      required: true

  - type: markdown
    attributes:
      value: "### Environment Information"

  - type: input
    attributes:
      label: "Operating System"
      placeholder: "e.g., Windows 10, macOS 12, Ubuntu 20.04"
      required: false

  - type: input
    attributes:
      label: "Node.js Version"
      placeholder: "e.g., 16.13.0"
      required: false

  - type: input
    attributes:
      label: "Browser (if applicable)"
      placeholder: "e.g., Chrome 95, Firefox 94"
      required: false

  - type: textarea
    attributes:
      label: "Screenshots/Logs"
      description: "Add any relevant screenshots, error messages, or logs"
      placeholder: "Paste error messages or attach screenshots here..."
      required: false

  - type: textarea
    attributes:
      label: "Additional Context"
      description: "Any other relevant information"
      placeholder: "Add any other context about the problem here..."
      required: false

  - type: checkboxes
    attributes:
      label: "Interested in Fixing?"
      options:
        - label: "I would like to submit a pull request to fix this issue"
