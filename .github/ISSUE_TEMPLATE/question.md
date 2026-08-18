name: "❓ Question/Discussion"
description: "Ask a question or start a discussion"
title: "[QUESTION] "
labels: ["question", "discussion"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        ## ❓ Question/Discussion
        Have a question? Need help? Start a discussion here!
        For general discussions, consider using [GitHub Discussions](https://github.com/samsonsimbeye01/simbeyepharm/discussions) instead.

  - type: textarea
    attributes:
      label: "Your Question"
      description: "What would you like to know?"
      placeholder: "Ask your question here..."
      required: true

  - type: textarea
    attributes:
      label: "Context"
      description: "Additional context to help us understand your question"
      placeholder: "What have you tried? What documentation have you read?"
      required: false

  - type: textarea
    attributes:
      label: "Expected Help"
      description: "What kind of help are you looking for?"
      placeholder: "Code example, documentation link, setup help, etc."
      required: false

  - type: checkboxes
    attributes:
      label: "Resources Checked"
      options:
        - label: "I have read the README.md"
        - label: "I have read the OVERVIEW.md"
        - label: "I have searched existing issues and discussions"
