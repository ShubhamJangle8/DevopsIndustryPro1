pipeline {
  agent {
    docker {
      image 'abhishekf5/maven-abhishek-docker-agent:v1'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' 
    }
  }
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
    stage('Static Code Analysis') {
      environment {
        SONAR_URL = "http://65.0.95.218:9000"
      }
      steps {
        withCredentials([string(credentialsId: 'sonarqube', variable: 'SONAR_AUTH_TOKEN')]) {
        sh 'mvn sonar:sonar -Dsonar.login=$SONAR_AUTH_TOKEN -Dsonar.host.url=${SONAR_URL}'
        }
      }
    }
  }
}
