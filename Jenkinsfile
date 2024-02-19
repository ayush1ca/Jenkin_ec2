pipeline {
    agent {
        any {
            // i  mage 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    // agent 
    tools {nodejs "node"}
    environment {
            CI = 'true'
        }
    stages {
        stage('Build') {
            steps {
                sh 'node -v'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deliver') {
            steps {
                sh 'npm run build'
                echo 'Visit http://localhost:3000 to see your Node.js/React application in action.'
                sh 'npm start'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                
            }
         }

    }
}