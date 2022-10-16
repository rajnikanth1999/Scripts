```yml
trigger:
- main
pool: default
jobs: 
    - job:
      steps:
      - task: Maven@3
        inputs: 
            mavenPomFile: pom.xml
            goals: clean package
            
```