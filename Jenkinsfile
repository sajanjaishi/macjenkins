pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-html-app')
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Here you can add test steps if needed
                    echo 'Testing...'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.image('my-html-app').run('-d -p 8081:80')
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
