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
                dir('path_to_your_repo_directory') {
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
                dir('path_to_your_repo_directory/powerbi-api-server') {
                    sh 'node index.js'
                }
            }
        }
    }
}
