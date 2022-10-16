```yml
trigger:
- main
pool: devops
jobs: 
    - job:
      steps:
      - task: DotNetCoreCLI@2
        displayName: Build
        inputs:
          command: build
      - task: DotNetCoreCLI@2
        inputs:
          command: 'publish'
        displayName: Publish
```