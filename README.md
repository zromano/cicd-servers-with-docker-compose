# CICD Servers With Docker Compose

A docker-compose file that can be used to start the following servers:
* GitLab-CE
* SonarQube
* GitLab Runner
* Jenkins

This was used to host a inter-connected ci/cd server on an AWS EC2 virtual machine.

GitLab was connected to SonarQube so that any change to the GitLab repo would cause the GitLab Runner 
to perform run a SonarScan and send the results to SonarQube.

Additionally, any update to GitLab's Container Registry would use webhooks to ping Jenkins to perform a Snyk scan of the 
image that changed in the container registry. This provided a way for user's to ensure they are only using secure containers
without having to remember to do any manual scanning.

Written by [Zach Romano](https://zromano.com)