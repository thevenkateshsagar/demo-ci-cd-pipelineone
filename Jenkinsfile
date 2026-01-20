pipeline {
    agent any
    
    environment {
        APP_ENV = 'production'
        APP_NAME = 'myapp'
        VERSION = '1.0.0'
    }

    stages {
        stage('checkout') {
            steps {
                echo "Checking out code..."
                sh 'git --version'
            }

        }
        stage('build') {
            steps {
                sh 'git log -1'
                sh 'ls -la'
            }
        }
        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'echo Build Successful'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing application...'
                sh 'echo Test Successful venkat'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying application to ${APP_ENV} environment..."
                echo "Application Name: ${APP_NAME}"
                echo "Application Version: ${VERSION}"
                sh 'echo Deploy Successful'
            }
        }
    }
}