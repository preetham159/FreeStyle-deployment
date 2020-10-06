pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
               git 'https://github.com/preetham159/TomcatDeployment'
            }
        }
        stage('Build using maven') {
            steps {
               sh 'mvn clean package'
            }
        }
        stage('Deployment') {
            steps {
               sshagent(['tomcat8']) {
            sh 'scp target/*.war ubuntu@13.127.180.117:/opt/tomcat8/webapps/'
             }
            }
        }
    }
}
