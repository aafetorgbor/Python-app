pipeline {
   agent {
  docker {
    image 'qnib/pytest:latest'
  }
}
    

    stages {
        
        
         stage('TEST') {
            steps {
               sh 'pytest -v'
       
            }
        }
        
     
        
         stage('DEPLOY') {
            steps {
                echo 'Deploying...'
            }
         }
        
        
        stage('slack notification sent'){
           steps{
               echo ' sending slack notification....'
               echo 'slack notification sent'
               
           }
         }
        
    }
    
    
}
