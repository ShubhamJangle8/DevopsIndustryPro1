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
                git branch: 'main', url: 'https://github.com/ShubhamJangle8/DevopsIndustryPro1.git'
            }
            
        }
    }
}
