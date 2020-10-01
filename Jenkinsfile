node{
   stage('SCM Checkoutt'){
   git 'https://github.com/febyjose/deploymentmvntomcat'
   }
   stage('Build'){
   sh 'mvn clean package'
   }
   stage('deploying to tomcat'){
   sshagent(['tomcat8']) {
   sh 'scp target/*.war ubuntu@172.31.35.24:/opt/tomcat8/webapps/'
}
   }
}
