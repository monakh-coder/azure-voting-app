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
                sh 'sudo -n docker compose build'
                // Add test steps here
            }
        }
    }
}
        