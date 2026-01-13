pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/singh-pranjal/simple-ci-cd.git'
            }
        }

        stage('Deploy to Nginx') {
            steps {
                sh '''
                sudo cp index.html /usr/share/nginx/html/index.html
                '''
            }
        }
    }
}

