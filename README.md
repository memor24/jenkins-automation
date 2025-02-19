# jenkins-automation
# Jenkins CICD as code
The idea is to manage the entire cicd infrastructure as code:
```
terraform fmt
terraform init

terraform validate
terraform plan

terraform apply
terraform destroy
```
## On-premise
Creates a fully automated cicd pipeline to deploy a python web app:
- Provision linux server by Terraform and deploys CICD automation code with Ansible roles
- Installs Jenkins and Groovy and runs the pipeline code
  
### Note on Jenkins installation
Java (runtime & compiler) is required to be installed for Jenkins to work.
```
java -version
javac -version
```
After running Ansible playbook, update the jenkins.service unit file:
```
sudo vi /etc/systemd/system/jenkins.service
# and add this info:
[Service]
User=devops
Group=jenkins
ExecStart=/usr/bin/java -jar /usr/share/jenkins/jenkins.war --httpPort=8085 --httpListenAddress=0.0.0.0
Restart=on-failure
```
----------------
## Cloud
The Jenkins server will be cloud based (ec2 or k8s)
