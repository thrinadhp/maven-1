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
}  
