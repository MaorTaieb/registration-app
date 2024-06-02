pipeline {
  agent { label 'jenkins ajent'}
  tools {
      jdk 'Java17'
      maven 'maven3'
   }
   stages {
       stage("Cleanapp Workspace") {
               steps {
               clieanWs()
               }
       }
       stage("check out from SCM ") {
               steps {
                   git branch: 'main', credentialsID: 'github' , url: 'https://github.com/maortaieb/register-app'
               }
       }
       stage("build application") {
               steps {
                   sh "mvn clean package"
               }
       }
      stage("test application") {
               steps {
                   sh "mvn tset"
               }
       }
   }
}
