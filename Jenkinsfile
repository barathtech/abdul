 pipeline {
    agent any
    stages {
        stage('gitclone') {
            steps { 
                sh'''npm install'''
                sh'''npm start index.js'''
            }
        }
      }
    }
