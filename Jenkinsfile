pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
                // Add build steps here
            }
        }
         
        stage('Docker Build') {
            steps {
                sh 'docker compose build'
                // Add test steps here
            }
        }
        stage('Start App') {
            steps {
                sh 'docker compose up -d'
                // Add deploy steps here
            }
        }
        stage('Run Tests') {
            steps {
                sh 'pytest ./tests/test_sample.py'
                // Add deploy steps here
            }
            post {
                success {
                    echo "Tests passed successfully."
                }
                failure {
                    echo "Tests failed."
                }
             }
        }
    }
    post{
        always {
            sh 'docker compose down'
        }
    }
}
        