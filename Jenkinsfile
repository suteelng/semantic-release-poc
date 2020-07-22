pipeline {
    agent { label 'java11' }
    stages {
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
    }
}