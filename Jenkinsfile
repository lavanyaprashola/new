pipeline { 
    agent any 
    environment {
    DOCKERHUB_CREDENTIALS = credentials('prashola-dockerhub') 
    }
        }
         stage( 'Login') { 
          steps{
          sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u SDOCKERHUB_CREDENTIALS_USR --password-stdin' 
          }
        }
        stage( 'Push'){ 
       steps { 
        sh 'docker push prashola/demo1:latest'
        }
       }
      }
        post { 
           always { 
           sh 'docker logout' 
         }
     }
  }

