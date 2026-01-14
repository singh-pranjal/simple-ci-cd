pipeline {
    agent any

    environment {
        IMAGE_NAME = "jenkins-docker-demo"
        CONTAINER_NAME = "jenkins-docker-container"
    }

    stages {
        stage('Build Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f $CONTAINER_NAME || true
                docker run -d -p 8081:80 --name $CONTAINER_NAME $IMAGE_NAME:latest
                '''
            }
        }
    }
}
