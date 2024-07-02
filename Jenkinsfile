pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                git url: 'https://github.com/Deepikasrini007/React_POC.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'cd /home/ubuntu/React_POC/powerbi-api-server && npm install'
            }
        }

        stage('Start Application') {
            steps {
                // Start the Node.js application
                sh 'cd /home/ubuntu/React_POC/powerbi-api-server && node index.js &'
            }
        }
    }
}
