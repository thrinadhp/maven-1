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
    sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.83.217:/var/lib/tomcat8/webapps/q2.war'
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
  stage('continuous delivery')
  {
  steps
  {
  input message: 'waiting for approval', submitter: 'admin'
  sh 'scp scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.89.142:/var/lib/tomcat8/webapps/p2.war'
  }
  }
 }
}
