node('master')
{
 stage('continuous download-master-branch')
  {
   git 'https://github.com/sivachanikyamiriyala/maven.git'
  }
 stage('continuousbuild-master-branch')
  {
   sh 'mvn package'
  }
 stage('continuousdeployment-master-branch')
  {
     sh 'scp /home/ubuntu/.jenkins/workspace/multibranch/webapp/target/webapp.war ubuntu@172.31.94.106:/var/lib/tomcat7/webapps/master.war'
  } 
}
