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
        stage("clean"){
            steps {
                sh "mvn clean"
            }
        }
        stage("compile"){
            steps {
                sh "mvn compile"
            }
        }
        stage("package"){
            steps {
                sh "mvn package"
                sh "mv target/*.war target/myweb.war"
            }
        }
        stage("deploy"){
            steps {
                sshagent(['tomcat']) {
                    // some block
                    sh """
                        scp -o StrictHostKeyChecking=no target/myweb.war ec2-user@3.110.62.75:/usr/share/tomcat/webapps
                    """
                }
            }
        }
    }
}
