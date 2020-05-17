pipeline {
    agent {
         docker {
            image 'node:latest' 
            args '-p 3000:3000' 
        }
    }
    environment { 
        CI = 'true'
    }
    stages {
        stage('Build') {
            stage('Build') { 
            steps {
                sh 'npm i --loglevel silent'
                sh 'npm cache clean --force'
                sh 'npm install --save core-js@^3'
                sh 'npm update [-g] [chokidar]'
                sh 'npm install gulp-sass --save-dev'
                sh 'npm install node-sass@latest'
                
                sh 'npm install'
            }
        }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    }
}
