pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mkdir -p build'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests"'
            }
        }

        stage('Validation') {
            steps {
                sh 'grep "Jenkins CI/CD Pipeline" build/index.html'
            }
        }
    }
}
