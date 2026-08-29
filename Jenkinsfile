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
                sh '''
                    mkdir -p build
                    cp index.html build/index.html
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests"'
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
        }
    }
}
