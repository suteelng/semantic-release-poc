pipeline {
    agent {
        docker {image 'adoptopenjdk:11-jre-hotspot'}
    }

    stages {
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
    }
}