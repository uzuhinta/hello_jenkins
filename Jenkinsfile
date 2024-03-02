pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/uzuhinta/hello_jenkins.git'
      }
    }
    stage('Build and push') {
      steps {
        // This step should not normally be used in your script. Consult the inline help for details.
        withDockerRegistry(credentialsId: 'dockerhub-id', url: 'https://index.docker.io/v1/') {
            bat 'docker build -t quannar178/hello-node:v10 .'
            bat 'docker push quannar178/hello-node:v10'
        }
      }
    }
  }
}