pipeline
{
agent any
stages
 {
  stage('continuous download')
  { 
   steps
   {
    git 'https://github.com/sivachanikyamiriyala/maven.git'
   }
  }
  stage('continuous build')
  {
   steps
   {
    sh 'mvn package'
   }
  }
  stage('continuous deployment')
  {
   steps
   {
    sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.83.217:/var/lib/tomcat8/webapps/q1q1.war'
   }
  }
  stage('continuous testing')
  {
   steps
   {
   git 'https://github.com/sivachanikyamiriyala/FunctionalTesting.git'
   sh 'java -jar testing.jar'
   }
  }
 }
 post
 {
 success
 {
  input message: 'waiting for approval', submitter: 'admin'
  sh 'scp  /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.89.142:/var/lib/tomcat8/webapps/p1p1.war'
 }
 failure
 {
  mail bcc: '', body: 'hi there all', cc: 'ravi@gmail.com', from: '', replyTo: '', subject: 'failed check once', to: 'sivachanikyamiriyala@gmail.com'
 }
 }
}
