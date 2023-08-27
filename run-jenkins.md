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
