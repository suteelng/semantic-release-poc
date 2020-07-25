pipeline {
    agent { label 'java11' }
    environment {
        GITEA_TOKEN = "0d52217a471423ba6210588baa607ae69135a342"
        GH_TOKEN = "0d52217a471423ba6210588baa607ae69135a342"
        NEXUS_USERNAME = "su"
        NEXUS = credentials('mydocker-userpass')
    }
    stages {
        stage("build") {
            steps {
             checkout([
                $class: 'GitSCM',
                branches: [[name: 'refs/heads/'+env.BRANCH_NAME]],
                extensions: [[$class: 'CloneOption', noTags: false, shallow: false, depth: 0, reference: '']],
                userRemoteConfigs: scm.userRemoteConfigs,
              ])
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
                echo "[INFO] GIT_BRANCH: ${env.GIT_BRANCH}"
                sh "GITEA_TOKEN=0d52217a471423ba6210588baa607ae69135a342 semantic-release"
            }
        }
    }
}