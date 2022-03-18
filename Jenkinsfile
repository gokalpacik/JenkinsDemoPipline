pipeline {
  agent any
  stages {
    stage('Restore packages') {
      steps {
        ls 

docker info 

docker build -t jenkins-demo:${BUILD_NUMBER} . 

docker tag jenkins-demo:${BUILD_NUMBER} jenkins-demo:latest 

docker images
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
