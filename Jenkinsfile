boolean flag = true
pipeline {
    agent any

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
            }
        }
        stage('Test') {
            when {
                expression {
                    flag == false
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
