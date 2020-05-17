pipeline {
    agent {
        docker {
            image 'node:latest' 
            args '-p 3001:3001' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm i --loglevel silent'
                sh 'npm cache clean --force'
                sh 'npm install --save core-js@^3'
                sh 'npm update [-g] [chokidar]'
                sh 'npm install gulp-sass --save-dev'
                sh 'npm install node-sass@latest'
                
                sh 'npm install --no-optional' 
                
            }
        }
    }
}
