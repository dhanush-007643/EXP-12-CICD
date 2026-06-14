pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Building Application...'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t flask-demo .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop flask-demo || exit 0'
                bat 'docker rm flask-demo || exit 0'
                bat 'docker run -d --name flask-demo -p 5000:5000 flask-demo'
            }
        }
    }
}SZ