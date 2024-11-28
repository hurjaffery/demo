boolean flag = true
pipeline {
    agent any
    parameters {
        // These are types of parameters
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Enable or disable tests')
    }
    environment {
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                // Using environment variable
                echo "Building version ${NEW_VERSION}"
                // Install Node.js using NVM
                sh "nvm install"
            }
        }
        stage('Test') {
            when {
                expression {
                    params.executeTests // Control test execution using parameter
                }
            }
            steps {
                echo 'Testing Project'
                // Here you can define commands for your tests
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Here you can define commands for your deployment
            }
        }
    }
    post {
        always {
            echo 'Post Build condition running'
        }
        failure {
            echo 'Post action if build failed'
        }
    }
}
