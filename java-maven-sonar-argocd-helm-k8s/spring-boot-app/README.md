sudo apt install unzip

sudo apt install maven

(SonarQube Server locally)

sudo su -
adduser sonarqube
sudo su - sonarqube

wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip

unzip sonarqube-9.4.0.54424.zip

chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424

chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424

cd sonarqube-9.4.0.54424/bin/linux-x86-64/

./sonar.sh start

(Access the `SonarQube Server` on `http://<ip-address>:9000`)

Jenkins Dashboard:

Manage Jenkins/Plugins/Available Plugins: Docker Pipeline and SonarQube scanner

Manage Jenkins/Manage credentials/system/global/add 1. github 2. sonarqube 3. docker
Jenkins/restart

Pipeline/scm/git/Jenkinsfile/apply

Buildnow


