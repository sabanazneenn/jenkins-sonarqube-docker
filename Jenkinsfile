pipeline {
    agent any

    stages {
        stage('git') {
            steps {
                git credentialsId: 'github-pat-cicd', url: 'https://github.com/sabanazneenn/jenkins-sonarqube-docker.git'
            }
        }
        stage('SCM') {
          checkout scm
        }
        stage('SonarQube Analysis') {
         def scannerHome = tool 'SonarScanner';
         withSonarQubeEnv() {
           sh "${scannerHome}/bin/sonar-scanner"
          }
         }
        } 
      }
     }
