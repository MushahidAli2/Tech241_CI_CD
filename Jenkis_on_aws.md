# Jenkins on AWS

## Installation Steps

1. `sudo apt update -y`
   - Updates the local package index on the system using the Advanced Package Tool (APT).
   
2. `sudo wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -`
   - Downloads the Jenkins repository key from the specified URL and adds it to the system's list of trusted keys.
   
3. `sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`
   - Adds the Jenkins repository URL to the APT sources list, allowing the system to fetch Jenkins packages from the repository.
   
4. `sudo apt update`
   - Updates the package index again to include the Jenkins repository after adding it in the previous step.
   
5. `sudo apt install jenkins`
   - Installs Jenkins on the system by fetching and installing the Jenkins package from the repository.
   
6. `wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -`
   - Downloads the Jenkins repository key again and adds it to the trusted keys list.
   
7. `sudo apt update`
   - Updates the package index to include the Jenkins repository after adding the key in the previous step.
   
8. `sudo apt install jenkins`
   - Installs Jenkins on the system by fetching and installing the Jenkins package from the repository.
   
9. `sudo apt upgrade -y`
   - Upgrades all installed packages on the system to their latest versions.
   
10. `wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -`
    - Downloads the Jenkins repository key for the stable version and adds it to the trusted keys list.
    
11. `sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'`
    - Adds the Jenkins stable version repository URL to the APT sources list.
    
12. `java -version`
    - Displays the version information for Java installed on the system.
    
13. `sudo apt install openjdk-11-jdk -y`
    - Installs OpenJDK 11 on the system, which is a required dependency for Jenkins.
    
14. `sudo apt update`
    - Updates the package index to include the Jenkins repository after adding it in the previous step.
    
15. `sudo apt install jenkins -y`
    - Installs Jenkins on the system by fetching and installing the Jenkins package from the repository.
    
16. `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 5BA31D57EF5975CA`
    - Retrieves the GPG key from the Ubuntu key server using the specified key ID.
    
17. `sudo apt update`
    - Updates the package index to include the Jenkins repository after adding the key in the previous step.
    
18. `sudo apt install jenkins -y`
    - Installs Jenkins on the system by fetching and installing the Jenkins package from the repository.
    
19. `jenkins --version`
    - Displays the version information for Jenkins installed on the system.
    
20. `sudo systemctl enable jenkins`
    - Enables Jenkins as a system service, allowing it to start automatically on system boot.
    
21. `sudo systemctl start jenkins`
    - Starts the Jenkins service immediately.
    
22. `sudo systemctl status jenkins`
    - Retrieves the status of the Jenkins service, providing information about its current state.
    
23. `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`
    - Displays the content of the initialAdminPassword file, which contains the administrator password for Jenkins
24. The Jenkins installation script directs you to the Customize Jenkins page. Click Install suggested plugins.

25. Once the installation is complete, the Create First Admin User will open. Enter your information, and then select Save and Continue.
Create your first admin user.

26. On the left-hand side, select Manage Jenkins, and then select Manage Plugins. Add any plugin you require
