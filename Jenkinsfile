pipeline { 
    agent any 
    environment {
    DOCKERHUB_CREDENTIALS = credentials('prashola-dockerhub') 
    }
    stages { 
        stage( 'Build') { 
        steps { 
         sh 'docker build -t  prashola/demo1:latest .' 
         }
        }
         stage( 'Login') { 
          steps{
          sh 'echo $0OCKERHUB_CREDENTIALS_PSW | docker login -u SDOCKERHUB_CREDENTIALS_USR --password-stdin' 
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

