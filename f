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
  sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.91.23:/var/lib/tomcat8/webapps/qa.war'
 }
 stage('continuous testing')
 {
 git 'https://github.com/sivachanikyamiriyala/FunctionalTesting.git'
 sh 'java -jar testing.jar'
 }
 stage('continuous delivery')
 {
  sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.89.73:/var/lib/tomcat8/webapps/pr.war'
 }

}
