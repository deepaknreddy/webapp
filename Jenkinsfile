#!groovy
pipeline {
  agent any
  stages {
    stage("to check ") {
      steps {
        script {
          sh 'echo "script run at $(date +%d-%m-%y-%T)" | sudo tee -a /home/centos/jenkins_build_history' 
        }//script
      }//steps
    } //stage("to check")
    
    stage("to build") {
      steps {
        script {
          sh 'mvn build'
        } //script
      } //steps
    } //stage("to build")
    
    stage("upload artefactory to nexus") {
      nexusArtifactUploader artifacts: [       // you can get this by using syntex generator option
        [
          artifactId: 'WebApp', 
          classifier: '', 
          file: 'target/WebApp.war', 
          type: 'war'
        ]
      ], 
        credentialsId: 'nexus3', 
        groupId: 'lu.amazon.aws.demo', 
        nexusUrl: '52.117.13.253:8081', 
        nexusVersion: 'nexus3', 
        protocol: 'http', 
        repository: 'my-project', 
        version: '1.0-SNAPSHOT'
    } // stage("upload artefactory to nexus")
  }// stages
} //pipeline
