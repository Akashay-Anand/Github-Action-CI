// Documenting github ci-cd concepts

# Github Action
// def
> tool to automate development and deployment lifecycle integrated in github website

> All GitHub Actions automations are handled using workflows. Every workflow consists of several core concepts: **events, jobs, steps, actions, and runners.**

// more info.
- GitHub Actions enables developers to automate workflows across issues, pull requests, and more
- The feature brings automation into the software development lifecycle using event-driven triggers, ranging from creating pull requests to building a new brand in a repository.

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


- You can build your own actions or reuse open-source actions available on the GitHub marketplace.