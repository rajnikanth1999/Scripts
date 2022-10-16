```groovy
pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                git 'https://github.com/rajnikanth1999/dotnetcore-docs-hello-world.git'
            }
        }
        stage ('clean package') {
            steps {
                sh '''
                dotnet build dotnetcoresample.csproj
                dotnet publish dotnetcoresample.csproj
                '''
            }
        }
        stage ('artifacts') {
            steps {
                archiveArtifacts artifacts: 'archive bin/Debug/net6.0/*.dll', followSymlinks: false
            }
        }
    }
}
```