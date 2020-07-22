pipeline {
    agent { label 'java11' }
    stages {
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
        stage("publish") {
            steps {
                withCredentials([usernamePassword(credentialsId: 'mydocker-userpass', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')

                ]){
                    sh "./gradlew jib -DsendCredentialsOverHttp=true -Djib.to.auth.username=${USERNAME} -Djib.to.auth.password=${PASSWORD}"
                }
            }
        }
    }
}