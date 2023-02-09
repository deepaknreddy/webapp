#!groovy
pipeline {
  agent any
  stages {
    stage("to check ") {
      steps {
        script {
          sh 'echo "script run at $(date +%d-%m-%y-%T)" >> /home/centos/jenkins_build_history' 
        }//script
      }//steps
    } //stage("to check")
  }// stages
} //pipeline
