# jenkins-automation
Jenkins CICD pipeline as code deployed with Ansible on a private server:

## On-premise
Creates a fully automated cicd pipeline to deploy a python web app:
- Provision linux server by Terraform and deploys CICD automation code with Ansible roles
- Installs Jenkins and Groovy and runs the pipeline code

### pipeline as code

The idea is to manage the entire CICD infrastructure as code. To initiate, run the Terraform
```
terraform init

terraform plan
terraform apply
```
----------------
## Cloud
The Jenkins server will be cloud based [ec2 with auto-scaling group](https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/) or ECS.
[Link](to aws-tf jenkins) 
