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

 }
}
