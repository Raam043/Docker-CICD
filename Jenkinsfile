```sh
pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/Raam043/Docker-CICD.git'
            }
        }
        stage('Docker Image Build') {
            steps {
                sh 'docker stop myapp & docker rm -f myapp & docker image rm -f myapp & docker build -t myapp .'
            }
        }
        stage('Docker Container Run') {
            steps {
                sh 'docker run -d --name myapp -p 80:80 myapp'
                sh 'docker tag myapp raam043/myapp:latest'
            }
        }
    }
}
```
