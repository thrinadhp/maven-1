node('master')
{
 stage('continuous download')
 {
   git git 'https://github.com/sivachanikyamiriyala/maven.git'
 }
 stage('continuous build')
 {
   sh 'mvn package'
 }

}
