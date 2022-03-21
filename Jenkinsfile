pipeline {
  agent any
  stages {
    stage('Restore packages') {
      steps {
        sh 'docker build . -t my-web-app -f JenkinsDemoPipline/Dockerfile'
      }
    }
  stage('Clean'){
    steps{
        sh "docker image ls"
     }
   }    
  
  }
}
