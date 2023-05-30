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

#### Hans-on 1 : *** Building in Jenkins**

* Install Jenkins on EC2

* Once logged in to Jenkins, click New Item in the left pane.

* From the list of available item types, select Folder.

* Click OK.

* Click Save to accept the default configurations for the folder.

* In the Test folder you just created, click the create new jobs link.

* In the Enter an item name field, type "user_test".

* From the list of available item types, make sure that Freestyle project is selected.

* Click OK.

* In the configuration for the project, scroll down to the Build section and click the Add build step drop-down arrow.

* From the drop-down menu, select Execute shell.

* In the Command text box, add the code containing the uname and whoami commands required to output the desired information to the requested file name:

> uname -a && whoami > user_test.txt

* Click Save.

* In the user_test project, click Build Now in the left pane.

* Verify that the build completes in the Build History pane.

* Once completed, click Workspace in the project pane.

* Click the view link to the right of the user_test.txt file.

* Verify that the output in the file displays jenkins.

* Click the back button in the browser window.

* Click on the drop-down arrow next to the build in the Build History pane and click Console Output.