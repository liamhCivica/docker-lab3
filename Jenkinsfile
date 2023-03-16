pipeline {
    agent any
    stages {
        stage('Clean up'){
            steps {
                sh "docker stop \$(docker ps -a -q)"
                sh "docker rm \$(docker ps -a -q)"
            }
        }
        stage('Build'){
            steps {
                sh "docker build -t app ."
            }
        }
        stage('Deploy'){
            steps {
                sh "docker run -p 5500:5500 --name app app"
            }
        }
    }
}
