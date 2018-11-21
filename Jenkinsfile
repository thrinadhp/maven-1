pipeline
 {
 agent any
 stages
   {
     stage('continuousdownload')
      {
        steps
	{
	 git 'https://github.com/sivachanikyamiriyala/maven.git'

	}
       }
      stage('continuousbuild')
      {
      steps
      {
      sh 'mvn package'
      }
      }
      stage('continuousdeployment')
      {
      steps
      {
         sh 'scp /home/ubuntu/.jenkins/workspace/declarativepipeline/webapp/target/webapp.war ubuntu@172.31.36.239:/var/lib/tomcat8/webapps/icici.war'

      }
      }
   }

 }
