// Documenting github ci-cd concepts

# Github Action
// def
> tool to automate development and deployment lifecycle integrated in github website

> All GitHub Actions automations are handled using workflows. Every workflow consists of several core concepts: **events, jobs, steps, actions, and runners.**

// more info.
- GitHub Actions enables developers to automate workflows across issues, pull requests, and more
- The feature brings automation into the software development lifecycle using event-driven triggers, ranging from creating pull requests to building a new brand in a repository.

### use Case of github action
- CI/CD
- Testing
- Notifications
- code Analysis

> note: migration coud be challenging if we swith somewhere else from github

## Workflows
> It is an specific folder we create inside ‘.github’ directory. And this file contains all required instruction for events

> Github monitor ‘.github’ file and ‘workflow’ and performs task which is there inside based on that condition

- uses a YAML file to define the various steps of a workflow. 
- 

## Where does this task runs:
> Github do provide(linux, windows, macOS) virtual machine and servers to which can be utilize with the help of API. 

> Can use our own self-hosted runners in our own data center or cloud

### Events
> Events are defined triggers that start a workflow, such as creating a branch, opening a pull request, or commenting on an issue.
- https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows 

### Jobs
> Jobs are tasks that are executed in a workflow when an event is triggered.

- Jobs can run in sequential order or in parallels(default).
- each job will run inside its own virtual machine runner, or insidea container
- jobs can ither run a script or run an action,

### Actions
> An action is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task

- You can build your own actions or reuse open-source actions available on the GitHub marketplace.

### Runner
- A runner is a series of tasks that are executed in a workflow when triggered by an event. Each runner is responsible for executing a single job.


```
GitHub Actions uses workflows, which are automated processes that are made up of jobs, events, actions and runners. Events are triggers that start a workflow, jobs are tasks executed in a workflow, when an event is triggered, actions are used to perform complex tasks that are imported into workflows, and runners execute a single job.
```

# Context 
> Contexts like github, env, and secrets provide dynamic data available throughout your workflow, influencing how steps are executed or what information is accessible.

## comprehensive list of contexts available within GitHub Actions workflows, organized by where they're accessible:

> Workflow-level contexts:

- github: Provides information about the GitHub event that triggered the workflow, the repository, the workflow itself, and more.
- env: Allows you to set environment variables that are available throughout the entire workflow.
- secrets: Contains sensitive information encrypted by GitHub, accessible securely within your workflow.
- inputs: Accesses input values provided when a workflow is triggered manually or from another workflow.

> Job-level contexts:

- needs: Specifies dependencies between jobs, ensuring one job completes successfully before another starts.
- strategy: (as discussed previously) Controls how multiple runs of a job are created and executed.
- matrix: Within strategy, defines a matrix of different configurations for a job to run against.
- inputs: Accesses input values passed to a specific job.
- vars: Sets variables that are only available within the job.

> Container-level contexts:

- needs: Specifies dependencies between container jobs.
- strategy: Controls how multiple runs of a container job are created and executed.
- matrix: Defines a matrix of different configurations for a container job to run against.
- env: Sets environment variables within the container.
- vars: Sets variables that are only available within the container.
- secrets: Accesses encrypted secrets within the container environment.
- inputs: Accesses input values passed to the container job.

> Steps-level contexts:

- runner: Provides information about the runner executing the step, such as its operating system and architecture.
- job: Accesses information about the job that the step is running in.
- steps: Exposes information about previous steps in the job.