pipeline {
    agent any
    stages {
      stage('Checkout') {
      	 steps{
           checkout scm
           } 
         }
      stage("Build") {
         steps{
          sh'''npm install'''
           sh'''npm start index.js'''
           }
         }
      stage('Test Plan') { 
          steps{
          withCredentials([string(credentialsId: "github.company.com-token", variable: "GITHUB_TOKEN")]) {
          echo "Getting the deploy repo ${paas.gitflow.to.git.repo.replace("github", GITHUB_TOKEN + ":@github")}"
          sh "git clone ${paas.gitflow.to.git.branch} ${paas.gitflow.to.git.repo.replace("github", GITHUB_TOKEN + ":@github")} ${paas.gitflow.to.git.cloneDir}"
          sh "ls -la ${paas.gitflow.to.git.cloneDir}"
        }
         }
       }
     }
   }
