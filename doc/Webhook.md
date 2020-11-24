# Webhook

## GitLab

Go to project settings -> Webhooks

URL: `http://jenkins:8080/jenkins/project/FOLDER/PROJECT_NAME/` (See [Webhook URL](https://github.com/jenkinsci/gitlab-plugin#webhook-url))

Trigger:

* Push events
* Merge request events

## SonarQube

Go to Administration -> Configuration -> Webhooks

name: jenkins

URL: `http://jenkins:8080/jenkins/sonarqube-webhook/`
