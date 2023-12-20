// working wth github workflow

> workflow is writen in YAML file, which follows python like structure.( * indentation)

```yml
name: hello_action # name of Action / which we sow in "github action" tab
run-name: runner_name 🚀 # name of instance
on: [push] # event which devine when to triger this workflow
jobs:   # defines what to do when get trigered (can contain multiple jobs)
  Explore-GitHub-Actions:  # job 1 ( jobs should have same indentation) ; performed on github server
    runs-on: ubuntu-latest # Os will be required to run tasks (github server; vm instance)
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code 
        uses: actions/checkout@v4 # lode file to server ; than we can perform various task there
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |                               # what is this ⁉️❓
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
  
  job-2: 
    build:
      ...
```
## we can access specific information from github using github object
## we can access specific information from server instance(runner) through runner object
```yml
owner name: ${{ github.actor }}
os: ${{ runner.os }}
```

## we can access output from steps
```yml
  run: echo "${{ steps.package.outputs.content }}"
```