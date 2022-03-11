 pipeline {
    agent any
    stages {
        stage('gitclone') {
            steps { 
                sh'''npm i'''
                sh'''npm run build'''
            }
        }
      }
    }
