pipeline { 
    agent any 
    environment {
    DOCKERHUB_CREDENTIALS = credentials('prashola-dockerhub') 
    }
    stages {
         stage( 'Login') { 
          steps{
          sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin' 
          }
        }
        stage( 'Push'){ 
       steps { 
        sh 'docker push prashola/mickeymouse:1.0'
        }
       }
      }
        post { 
           always { 
           sh 'docker logout' 
         }
     }
  }

