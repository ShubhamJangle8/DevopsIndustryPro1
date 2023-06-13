pipeline {
  agent {
    docker {
      image 'abhishekf5/maven-abhishek-docker-agent:v1'
      args '--user root -v /var/run/docker.sock:/var/run/docker.sock' 
    }
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
  }
}
