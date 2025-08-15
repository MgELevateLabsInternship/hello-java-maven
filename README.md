# Task-8

## Install or Run Jenkins

You can run Jenkins via Docker:
```
docker run -p 8080:8080 jenkins/jenkins:lts
```
After starting, get the initial admin password:
```
docker exec -it <container_name> cat /var/jenkins_home/secrets/initialAdminPassword
```

- Open Jenkins in browser: http://<server-ip>:8080
- Complete setup wizard and install Suggested Plugins.

## Install Java & Maven

If using Jenkins Docker:
- Go to Manage Jenkins → Global Tool Configuration
- Under JDK, add JDK 8 or 11 (check “Install automatically” if needed)
- Under Maven, add Maven (e.g., Maven 3.8.6) and select “Install automatically”.


##  Create Jenkins Job

- On Jenkins dashboard, click New Item
- Enter project name: Hello-Java-Maven
- Select Freestyle Project
- In Source Code Management:
- Option 1: Git → Add repository URL if stored in GitHub
- In Build Environment, ensure Provide Maven settings is enabled.
- In Build section:
```
Add Invoke top-level Maven targets
Set Goals:
clean package
```
## Build the Job

- Click Build Now
- Open Console Output and check for:
- [INFO] BUILD SUCCESS

## Screenshots:

Jenkins job configuration
<img width="1892" height="873" alt="ATS score checker - Brave 15-08-2025 19_49_21" src="https://github.com/user-attachments/assets/94de44ae-1c7b-47c2-922e-98bf7ce31734" />
<img width="1920" height="872" alt="Hello-Java-Maven Config - Jenkins - Brave 15-08-2025 19_49_25" src="https://github.com/user-attachments/assets/c513f132-2de4-4c54-88a0-4e6ea025e887" />

Console output showing BUILD SUCCESS
<img width="1920" height="876" alt="Hello-Java-Maven #2 Console - Jenkins - Brave 15-08-2025 19_48_42" src="https://github.com/user-attachments/assets/3e9c16c9-b48c-4dd5-bbd0-de15e3095215" />
<img width="1920" height="856" alt="Hello-Java-Maven #2 Console - Jenkins - Brave 15-08-2025 19_48_55" src="https://github.com/user-attachments/assets/a043de8e-c0dc-404b-ab8b-5a6d309d4898" />

