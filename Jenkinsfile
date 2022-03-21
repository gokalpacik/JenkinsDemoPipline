pipeline {
  agent any
  stages {
    stage('Restore packages') {
      steps {
        sh 'docker build -t shanem/spring-petclinic:latest JenkinsDemoPipline/ .
      }
    }
  stage('Clean'){
    steps{
        bat "dotnet clean JenkinsDemoPipline\\JenkinsDemoPipline.csproj"
     }
   }
    
  stage('Build'){
   steps{
      bat "dotnet build JenkinsDemoPipline\\JenkinsDemoPipline.csproj --configuration Release"
    }
 }
    
    stage('Publish'){
     steps{
       bat "dotnet publish JenkinsDemoPipline\\JenkinsDemoPipline.csproj "
     }
}
  }
}
