pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Simulate a failing test
                sh 'exit 1'   // For Linux/Mac agent
                // bat 'exit 1' // For Windows agent
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                archiveArtifacts artifacts: '**/*', allowEmptyArchive: true
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check logs.'
        }
    }
}
