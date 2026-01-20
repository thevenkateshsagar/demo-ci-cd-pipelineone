pipeline {
    agent any

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
    }
}