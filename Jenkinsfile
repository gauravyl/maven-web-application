node{
   
    def mavenHome = tool name: "maven 3.8.5"
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
   
    stage('CheckoutCode')
{
    git branch: 'development', credentialsId: 'e30d218e-b0cd-486b-98f0-ea1163f81463', url: 'https://github.com/gauravyl/maven-web-application.git'
}

    stage('Build')
    {
sh "${mavenHome}/bin/mvn clean package"
    }
    /*
    stage('ExecuteSonarQubeReport')
    {
sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    
    stage('UploadArtifactsIntoNexus')
    {
sh "${mavenHome}/bin/mvn deploy"
    }
    
    stage('DeployAppIntoTomcatServer')
    {
sshagent(['4dffdd44-0183-4343-a9b5-5d02bbdfcc02']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.45.10:/opt/apache-tomcat-9.0.63/webapps"

}
    }
    */
}
