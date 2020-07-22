pipeline {
    agent none
    stages {
        stage('Initialize'){
            steps {
                script {
                    def dockerHome = tool 'myDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
        }
        stage("build") {
            agent {
                docker {image 'jenkins/agent:latest-jdk11'}
            }
            steps {
                sh './gradlew test'
            }
        }
    }
}