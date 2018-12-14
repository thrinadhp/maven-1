node('master')
{    
    stage('continuousdownload-master')
    {
        git 'https://github.com/sivachanikyamiriyala/maven.git'
    }
    stage('continuousBuild-master')
    {
        sh 'mvn package'
    }
}
