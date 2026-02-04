pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
                // Add build steps here
            }
        }
         stage('Docker debug') {
            steps {
                sh '''
                    set -x
                    whoami
                    id
                    hostname
                    pwd
                    ls -l /var/run/docker.sock || true
                    getent group docker || true
                    groups || true
                    docker version || true
                    docker ps || true
                '''
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker compose build'
                // Add test steps here
            }
        }
       

    }
}
        