pipeline {
    agent { label 'java11' }
    environment {
        GITEA_TOKEN = "0d52217a471423ba6210588baa607ae69135a342"
    }
    stages {
        stage("build") {
            steps {
                sh './gradlew test'
            }
        }
//         stage("publish") {
//             steps {
//                 withCredentials([usernamePassword(credentialsId: 'mydocker-userpass', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')
//
//                 ]){
//                     sh "./gradlew jib -DsendCredentialsOverHttp=true -Djib.to.auth.username=${USERNAME} -Djib.to.auth.password=${PASSWORD}"
//                 }
//             }
//         }
        stage("release") {
            steps {
                sh "printenv"
                sh "semantic-release"
            }
        }
    }
}