   pipeline {
         agent {
          label "pod-custom"
        }
  stages {
      stage('Checkout') {
      steps {
        checkout scm
      }
    }
 stage("Build") {
           sh'''npm install'''
            sh'''index.js'''
    }
      stage('Test Plan') {
       steps {
	   
          withCredentials([string(credentialsId: 'github-api', variable: 'GITHUB_TOKEN')]) {
		    
            sh "curl -s -H \"Authorization: token ${GITHUB_TOKEN}\" -X POST -d '{\"body\": \"This is my first test comment from jenkins\",\"commit_id\": \"4d0f019b93c11f1fabc8313da4c461dbdbde1fd5\",\"path\": \"Jenkinsfile\",\"position\": 4}' \"https://github.***.com/api/v3/repos/***/${env.GIT_URL.tokenize("/")[-1].tokenize(".")[0]}/pulls/${PULL_REQUEST}/comments\""
  }
		 }
       }
     }

  } 
