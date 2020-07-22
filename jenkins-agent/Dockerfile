from jenkins/agent:latest-jdk11

user root

run apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs npm
RUN npm install semantic-release @semantic-release/exec @saithodev/semantic-release-gitea -g


user jenkins