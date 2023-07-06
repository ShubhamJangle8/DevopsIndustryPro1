pipeline {
    agent any
    environment {
        PATH = "usr/bin/mvn:$PATH"
    }
    stages {
        stage("welcome msg"){
            steps {
                echo "Welcome to demo pipeline"
            }
        }
        stage("git checkout"){
            steps {
                git 'https://github.com/ShubhamJangle8/DevopsIndustryPro1.git'
            }
        }
        stage("clean"){
            steps {
                sh "mvn clean"
            }
        }
    }
}
