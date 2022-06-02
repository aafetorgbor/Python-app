pipeline {
   agent any
    
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
    
       post('slack notificion sent'){
            always{
               cleanWs()
            }
        }
    
}
