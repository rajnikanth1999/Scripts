```groovy
pipeline {
    agent any
    stages {
        stage('clone') {
            steps {
                git 'https://github.com/shopizer-ecommerce/shopizer.git'
            }
        }
        stage ('clean package') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
```