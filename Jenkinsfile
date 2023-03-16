pipeline {
    agent any
    stages {
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
