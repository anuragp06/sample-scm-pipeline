@Library('my-shared-lib') _

pipeline {
    agent any

    environment {
        GITHUB_TOKEN = credentials('my-github-token')
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code (dummy step for SCM testing)"
            }
        }

        stage('Shared Library Demo') {
            steps {
                sayHello('Anurag from SCM pipeline')
            }
        }

        stage('Build') {
            steps {
                echo "Running build step from SCM Jenkinsfile..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Package') {
            steps {
                echo "Packaging artifact..."
            }
        }
    }

    post {
        always {
            echo "Pipeline finished. Cleaning up…"
        }
        success {
            echo "Pipeline succeeded!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
