pipeline {
    agent any
    stages {
        stage('build') {
            steps { 
                sh'''npm install'''
                sh'''npm start index.js'''
            }
        }
      def isPullRequest = false
if ( params.pullRequestID?.trim() )
{
  isPullRequest = true
  //do stuff to change how the pipeline should react.
}
    
      }
    }
