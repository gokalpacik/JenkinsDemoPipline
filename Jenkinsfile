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
         sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'  
        sh 'chmod u+x ./kubectl'  
        sh './kubectl apply'
     }
   }  
  
  }
}
