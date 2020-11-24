# GitLab

## Prerequisite

[Requirements](https://docs.gitlab.com/ee/install/requirements.html)

### Configuration (Server)

#### Network

Go to Admin Area -> Settings -> Network.

Check "Allow requests to the local network from web hooks and services".

Add `http://jenkins:8080/` to "Local IP addresses and domain names that hooks and services may access."

### Configuration (Local)

Edit the `config` file of your `.ssh` folder to add the following configuration

```
Host localhost
HostName localhost
Port 10022
User USER_NAME
```