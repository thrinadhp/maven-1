node('master')
{
    stage('continuousdownload')
    {
        git 'https://github.com/sivachanikyamiriyala/maven.git'
    }
    stage('continuousBuild')
    {
        sh 'mvn package'
    }
    stage('continuousDeployment')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/multibranch/webapp/target/webapp.war ubuntu@172.31.86.160:/var/lib/tomcat8/webapps/1.war'
    }
    stage('continuoustesting')
    {
        git 'https://github.com/sivachanikyamiriyala/FunctionalTesting.git'
        
    }
    stage('continuousdeployment')
    {
        input message: 'waiting for approval', submitter: 'admin'
        sh 'scp /home/ubuntu/.jenkins/workspace/multibranch/webapp/target/webapp.war ubuntu@172.31.93.75:/var/lib/tomcat8/webapps/1.war'
    }
}
