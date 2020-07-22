pipeline {
    agent {
        docker {image 'jenkins/agent:latest-jdk11'}
    }

    stages {
        stage('Initialize'){
            steps {
                def dockerHome = tool 'myDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
            }
        }
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
    }
}