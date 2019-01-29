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
  sh 'scp /home/ubuntu/.jenkins/workspace/multobranchpipeline_master/webapp/target/webapp.war ubuntu@172.31.83.217:/var/lib/tomcat8/webapps/11.war'
  }
  stage('continuous testing')
  {
  git 'https://github.com/sivachanikyamiriyala/maven.git'
  sh 'java -jar testing.jar'
  }
  stage('continuous delivery')
  {
    sh 'scp /home/ubuntu/.jenkins/workspace/multobranchpipeline_master/webapp/target/webapp.war ubuntu@ 172.31.89.142:/var/lib/tomcat8/webapps/2222.war'
  }
}
