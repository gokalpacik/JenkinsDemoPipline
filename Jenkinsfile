pipeline {
  agent any
  stages {
    stage('Restore packages') {
      steps {
        sh 'docker build . -t jenkinspipelinedemo:latest -f JenkinsDemoPipline/Dockerfile'
      }
    }
  stage('Clean'){
    steps{
        sh "docker image ls"
     }
   }    
    
    stage('Run'){
    steps{
        sh "docker run -p 8081:80 jenkinspipelinedemo:latest"
     }
   }  
  
  }
}
