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
- Unlock jenkins by finding the **admin** password that jenkins write to the stdio.  
Example:  
dd19cc0a01724ea2a50d2789605d6e0a
- Browse to localhost:8080 and Jenkins will suggest plugins to be installed for you.  
Click on **install suggested plugins** and wait until all plugins are installed.