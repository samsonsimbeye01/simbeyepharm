name: "✨ Feature Request"
description: "Suggest a new feature or enhancement"
title: "[FEATURE] "
labels: ["enhancement", "feature-request"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        ## ✨ Feature Request
        Thank you for suggesting an improvement! Please provide details about the feature you'd like to see.

  - type: checkboxes
    attributes:
      label: "Prerequisites"
      description: "Please check the following:"
      options:
        - label: "I have searched existing feature requests and this is not a duplicate"
          required: true
        - label: "This feature aligns with the project's scope"
          required: false

  - type: textarea
    attributes:
      label: "Feature Description"
      description: "Clear description of the requested feature"
      placeholder: "Describe the feature you'd like to see..."
      required: true

  - type: textarea
    attributes:
      label: "Problem Statement"
      description: "What problem does this feature solve?"
      placeholder: "This feature would help users by..."
      required: true

  - type: textarea
    attributes:
      label: "Proposed Solution"
      description: "How should this feature work?"
      placeholder: "The feature should work like this..."
      required: false

  - type: textarea
    attributes:
      label: "Example Usage"
      description: "Show how users would interact with this feature"
      placeholder: |
        Example code or user flow:
        ```
        User clicks "X" -> System does "Y" -> Result is "Z"
        ```
      required: false

  - type: textarea
    attributes:
      label: "Benefits"
      description: "Why is this feature valuable?"
      placeholder: |
        - Improves user experience by...
        - Solves the problem of...
        - Aligns with roadmap goal of...
      required: false

  - type: textarea
    attributes:
      label: "Additional Context"
      description: "Any other relevant information"
      placeholder: "Links, references, or related features..."
      required: false

  - type: checkboxes
    attributes:
      label: "Implementation"
      options:
        - label: "I would like to implement this feature"
