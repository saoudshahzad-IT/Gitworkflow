
name: First Workflow

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
  workflow_dispatch:

jobs:
  first-job:
    name: Run First Job
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Display Welcome Message
        run: echo "Hello! My first GitHub Actions workflow is running."

      - name: Show Repository Information
        run: |
          echo "Repository: $GITHUB_REPOSITORY"
          echo "Branch or Ref: $GITHUB_REF"
          echo "Workflow: $GITHUB_WORKFLOW"

      - name: List Repository Files
        run: ls -la
