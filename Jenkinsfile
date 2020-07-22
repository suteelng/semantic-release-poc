pipeline {
    agent { label 'java11' }
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
            steps {
                sh './gradlew test'
            }
        }
    }
}