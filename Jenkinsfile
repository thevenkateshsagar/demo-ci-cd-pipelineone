pipeline {
    agent any
    
    parameters {
        string(
            name: 'DEPLOY_ENV',
            defaultValue: 'main',
            description: 'Environment to deploy (main/staging)'
        )
        
        choice(
            name: 'BUILD_TYPE',
            choices: ['main', 'staging', 'production'],
            description: 'Select build type'
        )
        
        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run unit tests?'
        )
        
        text(
            name: 'RELEASE_NOTES',
            defaultValue: 'Bug fixes and improvements',
            description: 'Enter release notes'
        )
    }
    
    stages {
        stage('Display Parameters') {
            steps {
                echo "🎯 Deployment Environment: ${params.DEPLOY_ENV}"
                echo "🔧 Build Type: ${params.BUILD_TYPE}"
                echo "🧪 Run Tests: ${params.RUN_TESTS}"
                echo "📝 Release Notes: ${params.RELEASE_NOTES}"
            }
        }
        
        stage('Conditional Test Execution') {
            when {
                expression { params.RUN_TESTS == true }
            }
            steps {
                echo '🧪 Running tests as requested...'
                sh 'sleep 2'
                echo '✅ Tests completed'
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    if (params.DEPLOY_ENV == 'main') {
                        echo '⚠️  PRODUCTION DEPLOYMENT'
                        input message: 'Are you sure you want to deploy to PRODUCTION?', 
                              ok: 'Deploy'
                    }
                    echo "🚀 Deploying ${params.BUILD_TYPE} build to ${params.DEPLOY_ENV}..."
                }
            }
        }
    }
}