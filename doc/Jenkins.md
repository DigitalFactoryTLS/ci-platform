# Jenkins

## Installing

[Unlocking Jenkins](https://www.jenkins.io/doc/book/installing/docker/#unlocking-jenkins)

## Administration

### Plugins

Go to [Plugins](http://localhost:8080/jenkins/pluginManager/) ans install the following plugins:

* [Pipeline: Declarative](https://plugins.jenkins.io/pipeline-model-definition/)
* [Pipeline Utility Steps](https://plugins.jenkins.io/pipeline-utility-steps/)
* [GitLab](https://plugins.jenkins.io/gitlab-plugin/)
* [SonarQube Scanner](https://plugins.jenkins.io/sonar/)
* [NodeJS](https://plugins.jenkins.io/nodejs/)
* [JUnit](https://plugins.jenkins.io/junit/)
* [Clover](https://plugins.jenkins.io/clover/)
* [Timestamper](https://plugins.jenkins.io/timestamper/)
* [Workspace Cleanup Plugin](https://plugins.jenkins.io/ws-cleanup/)

### Credentials

Go to [Credentials](http://localhost:8080/jenkins/credentials/)

#### GitLab

Follow the [official documentation](https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html) to create a personal access token with the following rights:

* api
* read_repository
* write_repository
* read_registry
* write_registry

Create a GitLab API token and an user/password credential with the token generated.

#### SonarQube

Follow the [official documentation](https://docs.sonarqube.org/latest/user-guide/user-token/) to create a token.

Create a Secret text credential with the token generated.

### Configuration

Go to [Configuration](http://localhost:8080/jenkins/configure).

#### Pipeline Speed/Durability Settings

Pipeline Default Speed/Durability Level: Performance-optimized

#### SonarQube servers

Name: SonarQube

Server URL: `http://sonarqube:9000/`

Server authentication token: Use the credential created previously.

#### GitLab

Connection name: GitLab

GitLab host URL: `http://gitlab/`

Credentials: Use the credential created previously.

### Global Tools

Go to [Global Tools](http://localhost:8080/jenkins/configureTools/).

#### SonarQube Scanner

Name: SonarQube Scanner

✅ Install automatically

#### NodeJS

Name: NodeJS

✅ Install automatically

### Job

Create a multibranch pipeline

#### Branch Sources

Project Repository: `http://gitlab/PROJECT/REPOSITORY.git`

Credentials: Use the credential created previously.

Behaviours: Discover branches

#### Scan Pipeline Multibranches Triggers

✅ Periodically if not otherwise run

Interval: 1 day

#### Orphaned Item Strategy

✅ Discard old items

Days to keep old items: 2
