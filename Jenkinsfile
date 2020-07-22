pipeline {
    agent { label 'java11' }
    environment {
        GITEA_TOKEN = "0d52217a471423ba6210588baa607ae69135a342"
        GH_TOKEN = "0d52217a471423ba6210588baa607ae69135a342"
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
        stage("release") {
            steps {
                echo "[INFO] GIT_BRANCH: ${env.GIT_BRANCH}"
                sh "GITEA_TOKEN=0d52217a471423ba6210588baa607ae69135a342 semantic-release"
            }
        }
    }
}