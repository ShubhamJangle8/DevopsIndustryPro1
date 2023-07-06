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
        stage("commit"){
            steps {
                git branch: 'main', credentialsId: '86230c13-2ee9-4bda-8ddf-a5067ac76d20', url: 'https://github.com/ShubhamJangle8/DevopsIndustryPro1.git'
            }
            
        }
    }
}
