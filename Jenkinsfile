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
}
