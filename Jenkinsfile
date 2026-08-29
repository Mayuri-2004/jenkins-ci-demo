pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'mkdir -p build'
                sh 'cp index.html build/index.html'
                echo 'Build completed successfully.'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application tests...'
                sh 'test -f build/index.html'
                grep "Jenkins CI/CD Pipeline" build/index.html
                echo 'Tests passed successfully.'
            }
        }

        stage('Validation') {
            steps {
                echo 'Running additional validation...'
                sh 'test -s build/index.html'
                echo 'Validation successful.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check Console Output.'
        }
    }
}
               
