#!/bin/sh
# Create a redhat server in aws with at least 4GB of RAM
# sudo -i = become the root users
sudo hostname maven
cd /opt

sudo hostname maven
cd /opt
sudo yum install wget nano tree unzip git-all -y
sudo yum install java-11-openjdk-devel java-1.8.0-openjdk-devel -y
java -version
git --version

# Step 1. Download the Maven Software

# Step 2.
sudo wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.zip
sudo unzip apache-maven-3.8.6-bin.zip
sudo rm -rf apache-maven-3.8.6-bin.zip
sudo mv apache-maven-3.8.6/ maven

# Step 3. Set Environmental Variable ......... For Specific User
#vi ~/.bash_profile
echo "export M2_HOME=/opt/maven"  >>  ~/.bash_profile
echo "export PATH=$PATH:$M2_HOME/bin"   >> ~/.bash_profile

source ~/.bash_profile
mvn -version
