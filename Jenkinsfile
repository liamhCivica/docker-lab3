pipeline {
    agent any
    stages {
        stage('Clean up'){
            steps {
                sh '''
                $CONTAINERS=$(docker ps -a -q)
                echo $CONTAINERS
                if [ -n "$CONTAINERS" ]; then
                    docker stop app
                    docker rm app
                fi
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
