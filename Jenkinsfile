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
                git 'https://github.com/ShubhamJangle8/DevopsIndustryPro1.git'
            }
            
        }
    }
}
