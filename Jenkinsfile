pipeline {
    agent any
    stages {
        stage('Clean up'){
            steps {
                sh '''
                docker stop app || true && docker rm app || true
                '''
            }
        }
        stage('Build'){
            steps {
                sh "docker build -t app ."
            }
        }
        stage('Deploy'){
            steps {
                sh "docker run -d -p 5500:5500 --name app app"
            }
        }
    }
}
