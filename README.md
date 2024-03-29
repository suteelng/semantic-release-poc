

docker login mydocker:8082

Enable docker login:

Enable the Docker Bearer Token Realm in Nexus Security->Realms Tab


## Try upload to private docker registry

Add configuration in `build.gradle`

```
./gradlew jib -DsendCredentialsOverHttp=true
```

### install

```sh
sudo apt-get install node npm
sudo npm install semantic-release @semantic-release/exec -g
sudo npm install @saithodev/semantic-release-gitea -g
```

### Configuration

Authentication 

- Authentication go git to push git tags
   environment variable: `GH_TOKEN` =  ebef24dfee2e76abe415cdb59b8342b929ef7927    
- `GIT_CREDENTIALS`: URL encoded <username>:<password>, The username and password must each be individually URL encoded.
- SSH

Jenkins token: 11f16d1ee4c0d19ba1622e3fefbfd39052

```shell script
export GITEA_TOKEN=0d52217a471423ba6210588baa607ae69135a342
```

GITEA_URL: http://gitea:3000

## Config Jenkins

- Install Gitea plugin
- Config multi-branch pipeline with git repo (using git)
- Create agent:
    `Manage Nodes and Clouds` -> new Node. Give name and select permanent agent. Next. 
    Remote root directory: /home/jenkins/agent
    save and jenkins will shows start up command. Copy the command to run it in slave jenkins
    https://hub.docker.com/r/jenkins/agent

Build jenkins agent with nodejs support
```shell script
docker build -t jenkins-agent:jdk11-sr .
```

Note: also need to set GH_TOKEN

### Docker registry credential

There is no way to pass variables from jenkins into semantic-release plugins. Tried to use environment variables
with `env`. But `semantic-release/exec` plugin failed to read `env` variables.

The solution is to use Jib gradle `image.to.auth` configuration in `build.gradle` to read system environment variables.

