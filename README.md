

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
sudo npm install semantic-release -g
```

### Configuration

Authentication 

- Authentication go git to push git tags
   environment variable: `GH_TOKEN` =  ebef24dfee2e76abe415cdb59b8342b929ef7927    
- `GIT_CREDENTIALS`: URL encoded <username>:<password>, The username and password must each be individually URL encoded.
- SSH

Jenkins token: 11f16d1ee4c0d19ba1622e3fefbfd39052

```shell script
export GITEA_TOKEN: 0d52217a471423ba6210588baa607ae69135a342
```

GITEA_URL: http://localhost:3000
