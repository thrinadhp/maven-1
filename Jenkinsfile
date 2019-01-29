node('master')
 {
 stage('continuous download')
  {
  git 'https://github.com/sivachanikyamiriyala/maven.git'
  }
  stage('continuous build')
  {
  sh 'mvn package'
  }
  stage('continuous deployment')
  {
   sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.83.217:/var/lib/tomcat8/webapps/qaqa.war'
  }
  stage('continuous testing')
  {
  git 'https://github.com/sivachanikyamiriyala/FunctionalTesting.git'
  sh 'java -jar testing.jar'
  }
  stage('continuous delivery')
  {
   input message: 'waiting for approval', submitter: 'admin'
   sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.89.142:/var/lib/tomcat8/webapps/pppp.war'
  }
 }
