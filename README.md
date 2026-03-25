To run jenkins as a container run below command.

1. With Docker
```bash
docker run -d \
  --name jenkins \
  -p 8080:8080 \
  -p 50000:50000 \
  jenkins/jenkins:lts
```
2. With Podman
```bash
podman volume create jenkins_home
podman run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
```
3. Find the jenkins admin password
```bash
podman exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
4. Access the browser on **localhost:8080** and provide the Jenkins admin password to proceed with installation.
