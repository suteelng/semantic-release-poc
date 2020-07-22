pipeline {
    agent {
        docker {image 'jenkins/agent:latest-jdk11'}
    }

    stages {
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
    }
}