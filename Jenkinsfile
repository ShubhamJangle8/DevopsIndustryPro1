pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps('Checkout') {
        sh 'echo passed'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Unit Test') {
      steps {
        sh 'mvn test'
      }
    }
  }
}
