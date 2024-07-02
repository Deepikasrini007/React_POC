pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository
                checkout scm
            }
        }

        stage('Unzip and Setup') {
            steps {
                // Navigate to the repository directory
                dir('/home/ubuntu/React_POC') {
                    // Unzip the powerbi-api-server zip file
                    sh 'unzip powerbi-api-server.zip -d powerbi-api-server'

                    // Move into the unzipped directory
                    dir('powerbi-api-server') {
                        // Install dependencies
                        sh 'npm install'
                    }
                }
            }
        }

        stage('Start Application') {
            steps {
                // Start the application
                dir('/home/ubuntu/React_POC/powerbi-api-server') {
                    sh 'node index.js'
                }
            }
        }
    }
}
