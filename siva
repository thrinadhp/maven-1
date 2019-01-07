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
       sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.91.23:/var/lib/tomcat8/webapps/q.war'
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
      input message: 'waiting for approval', submitter: 'ravi'
      sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.89.73:/var/lib/tomcat8/webapps/q.war'
    }
  failure 
    {
         mail bcc: '', body: '', cc: 'wdjafbcwe;i', from: '', replyTo: '', subject: '', to: 'sivachanikyamiriyala@gmail.com'
    }  
  }

}
