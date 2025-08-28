# cycletest
Basic repository to build a pipeline using GitHub Actions

1. Create a GitHub Repository:

    Navigate to your GitHub dashboard.
    Click the "New" button to create a new repository.
    Provide a repository name and an optional description.
    Select the desired visibility (public or private).
    Optionally, initialize the repository with a README file.
    Click "Create repository."

2. Add a GitHub Actions Workflow:

    In your newly created repository, navigate to the "Actions" tab.
    Click on "New workflow" or choose a starter workflow suggested by GitHub.
    If starting from scratch, you will be presented with an editor to define your workflow in a YAML file. This file will be located in the .github/workflows/ directory of your repository.
    For a basic "Hello World" example, you can use the following YAML content:

Code

    name: Hello World Workflow

    on: [push] # This workflow runs on every push to the repository

    jobs:
      build:
        name: Say Hello
        runs-on: ubuntu-latest # The type of machine to run the job on

        steps:
          - uses: actions/checkout@v4 # Checks out your repository under $GITHUB_WORKSPACE, so your workflow can access it
          - name: Print Hello Message
            run: echo "Hello from GitHub Actions!" # Executes a shell command

    Commit the new workflow file to your repository.

3. Trigger and Observe the Workflow:

    Push a change to your repository (e.g., modify the README or add a new file). This will trigger the workflow defined in the on: [push] event.
    Navigate back to the "Actions" tab in your repository.
    You will see a new workflow run listed. Click on it to view the details of the job and its steps, including the output of the "Print Hello Message" step.
