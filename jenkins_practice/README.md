### Jenkins installation

* Create an EC2 instance on AWS.

* ssh to the EC2 your created.

* install Java: 
> sudo yum install -y java-11-openjdk

* install wget: 
> sudo yum install -y wget

* Download the repo: 
> sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

* Import the required key: 
> sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

* Install Jenkins: 
> sudo yum install -y jenkins

* Enable Jenkins:
> sudo systemctl enable jenkins

* Start Jenkins:
> sudo systemctl start jenkins

* In a new browser tab, navigate to http://<PUBLIC_IP_ADDRESS>:8080, replacing <PUBLIC_IP_ADDRESS> with the IP address of the EC2 provided.

* We'll be taken to an Unlock Jenkins page telling us we need to locate the password. In the terminal, run:
> sudo cat /var/lib/jenkins/secrets/initialAdminPassword

* Copy the result of the command, as this is the password we need.

* Paste the password into the Administrator password field on the Jenkins browser page.

* Click Continue.

* Click Install suggested plugins. Note: If the install of any plugins fails, just wait a moment and click retry.

* Create a new user with your own information.

* Click Save and Continue.

* Click Save and Finish.

* Click Start using Jenkins.