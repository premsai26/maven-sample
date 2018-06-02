pipeline {
   agent {
    dockerfile {
      filename "Dockerfile"
      label "docker-nodes"
      args "-v /tmp:/tmp"
    }
  }
 stages {
 stage('Checkout') {
 steps {
 checkout scm
 }
 }
 stage('Build') {
 steps {
 sh "mvn clean compile"
 }
 }
 }
}  
