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
 }
