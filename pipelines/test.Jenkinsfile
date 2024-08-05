pipeline {
    agent any

    triggers {
        pullRequest()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                echo "Running tests for NetflixFrontend..."
                // Add actual test commands here
            }
        }
    }

    post {
        success {
            echo "Tests passed successfully!"
        }
        failure {
            echo "Tests failed. Please check the logs for more information."
        }
    }
}