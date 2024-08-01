
### (Install Java)

sudo apt update

sudo apt install fontconfig openjdk-17-jre

java -version

### (Now, you can proceed with installing Jenkins)

curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

// sudo apt-get update (optional)

sudo apt-get install jenkins

sudo systemctl enable jenkins

sudo systemctl start jenkins

(chrome: publicIP:8080)

(sudo cat /var/lib/jenkins/.... copy pwd and paste in dashboard)

(Install Plugins)

### (Run the below command to Install Docker)

// sudo apt update (optional)

sudo apt install docker.io
 
(Grant Jenkins user and Ubuntu user permission to docker deamon)

sudo su - 

usermod -aG docker jenkins

usermod -aG docker ubuntu

systemctl restart docker

### Install Maven and Unzip

sudo apt install unzip

sudo apt install maven

### (SonarQube Server locally)

sudo su -

adduser sonarqube

sudo su - sonarqube

wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip

unzip sonarqube-9.4.0.54424.zip

chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424

chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424

cd sonarqube-9.4.0.54424/bin/linux-x86-64/

./sonar.sh start

### (Access the SonarQube Server on http://<ip-address>:9000&& generate token)

### Jenkins Dashboard:

Manage Jenkins/Plugins/Available Plugins: Docker Pipeline and SonarQube scanner

Manage Jenkins/Manage credentials/system/global/add 1. github (secret text) 2. sonarqube (secret text) 3. docker (user name and password)

Jenkins dashboard/restart

Pipeline/scm/git/Jenkinsfile/apply

Buildnow
