 pipeline {
    agent any
    stages {
        stage('gitclone') {
            steps { 
                sh'''npm install'''
                 sh'''npm i -g pm2'''
                sh'''pm2 start index.js'''
            }
        }
      }
    }
