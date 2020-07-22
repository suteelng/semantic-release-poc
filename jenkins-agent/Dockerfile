FROM jenkins/agent:latest-jdk11

USER root

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash -
RUN apt-get install -y nodejs
RUN npm install semantic-release @semantic-release/exec @saithodev/semantic-release-gitea -g


USER jenkins