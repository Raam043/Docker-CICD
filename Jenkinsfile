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
                sh 'docker stop kiran & docker rm -f kiran & docker image rm -f kiran & docker build -t kiran .'
            }
        }
        stage('Docker Container Run') {
            steps {
                sh 'docker run -d --name kiran -p 80:80 kiran'
                sh 'docker tag kiran raam043/kiran:latest'
            }
        }
        stage('Docker Push to DockerHub') {
            steps {
                withCredentials([string(credentialsId: 'DH', variable: 'DH')]) {
                    sh 'docker login -u raam043 -p ${DH}'
                    sh 'docker push raam043/kiran:latest'
            }
        }
        }
    }
}
```
