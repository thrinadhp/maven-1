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
	  sh 'scp /home/ubuntu/.jenkins/workspace/multibranch_master/webapp/target/webapp.war ubuntu@172.31.91.23:/var/lib/tomcat8/webapps/mastersiva.war'
        }
     }
  }
}
