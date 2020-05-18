<details><summary>Use jenkins docker container</summary>

```bash
docker -v
docker-compose -v
# loads the docker-compose.yml file which launches
# docker container version of jenkins
docker-compose up
# Check code into repo
git init
git add .
git commit -m 'Initial commit'
git remote add origin https://github.com/shawfire/jekins-devops-microservice.git
git push -u origin master
```

- Access jenkins console via localhost:8001
- install suggested plugins
- create repo `jenkins-devops-microservice`
- Create jenkins user `admin`
- Manage Jenkins -> Global Tools Configuration -> Add Maven (myMaven) and Docker (myDocker) with `Install automatically` checked
- Jenkins -> Create a new job -> `jenkins-devops-microservice-pipeline` -> Pipeline

  - Build Triggers -> `Poll SCM` -> \* \* \* \* _ every minute (15 _ \* \* \* or every 15 minutes)
  - Pipeline -> Pipeline script from SCM -> provide the `githubUrl` -> `Jenkinsfile` contains configuration by default.

- Reference: jenkins.co

</details>
