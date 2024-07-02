pipeline {
    agent any
    environment {
        DEPLOYMENT_SERVER = "172.31.17.155"
        SSH_CREDENTAILSID = "React_App"
    }

   //  stages {
    //     stage('Checkout') {
     //       steps {
                // Checkout the repository
        //        checkout scm
       //     }
      //  }

        stage('SSH into Server') {
            steps {
                script {
                    sshcommend remote: [
                        allowAnyHosts: true,
                        failOnError: true,
                        host: "${env.DEPLOYMENT_SERVER}",
                        username: 'ubuntu'
                        credentialsId: "${env.SSH_CREDENTAILSID}"
                        ], command: ''
                    cd /home/ubuntu/React_POC/powerbi-api-server
                    npm install
                    node index.js
                }
            }
        }
}

        // stage('Start Application') {
            / steps {
                // Start the application
                // dir('/home/ubuntu/React_POC/powerbi-api-server') {
                   //  sh 'node index.js'
               //  }
           //  }
    // }
   // }
// }
