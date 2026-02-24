pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('flask-app')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('flask-app').inside {
                        sh 'echo "No tests available"'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.image('flask-app').run('-p 5000:5000')
                }
            }
        }
    }
}

