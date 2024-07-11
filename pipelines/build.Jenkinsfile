pipeline {
    agent {
        label 'general'
    }

    triggers {
        githubPush()
    }

    environment {
        DOCKER_IMAGE = 'netflix-front'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
            }
        }

        stage('Build app container') {
            steps {
                script {
                    // List files in the pipeline workdir
                    sh 'ls -al'

                    // Build the Docker image
                    sh 'docker build -t $DOCKER_IMAGE .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Example test command (replace with your actual test commands)
                    sh 'echo "Running tests..."'
                    // e.g., sh './run_tests.sh' for a script or docker run command for a containerized test
                }
            }
        }
    }

    post {
        always {
            // Clean up any resources or perform steps that should always happen
            echo 'Cleaning up...'
        }

        success {
            // Actions to take if the build succeeds
            echo 'Build succeeded!'
        }

        failure {
            // Actions to take if the build fails
            echo 'Build failed!'
        }
    }
}
