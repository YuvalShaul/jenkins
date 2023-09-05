# Run Jenkins (docker)

In this lab we're going to run Jenkins as a docker dontainer

## Create a volume

Let's create a docker volume, so that our docker container can save its configuration:
```
docker volume create jenkins-data
```
The docker volume is going to be saved under..
You can inspect the volume like this:
```
docker volume inspect jenkins-data
```
(not where docker keeps its volumes)

## Running a Jenkins container

Use this command:
```
sudo docker run -p 8080:8080 -p 50000:50000 -v jenkins-data:/var/jenkins_home jenkins/jenkins
```

## Post Run

- Browse jenkins using localhost:8080
- **Unlock jenkins** by finding the **admin** password that jenkins write to the stdio.  
Example:  
dd19cc0a01724ea2a50d2789605d6e0a
- **Install suggested plugins**:  
Browse to localhost:8080 and Jenkins will suggest plugins to be installed for you.  
lick on **install suggested plugins** and wait until all plugins are installed.
- **Add admin user**  
Add the details of an admin user (it is not recommended to use the **admin** that was already created)
- Configure the URL:  
You can leave that as **http://localhost:8080/** but make sure that the Jenkins werver can access itself using this url
- You'll get **Jenkins is ready** message, so click **Start using Jenkins**
