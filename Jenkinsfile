pipeline {
   agent any
    
    stages {
       
         stage('BUILD') {
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
               echo 'Slack notification sent'
               
           }
         }
        
    }
    
       post('slack notificion sent'){
            always{
               cleanWs()
            }
        }
    
}
