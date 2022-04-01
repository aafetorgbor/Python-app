pipeline {
    agent any
    

    stages {
        
     
         stage('BUILD') {
            steps {
               
               echo 'Building...' 
            }
        }
        
         stage('TEST') {
            steps {
                
                sh 'pytest -v'
            }
         }
         
         stage('DEPLOY') {
             steps {
                 
                 echo 'Deployihng'
                 sh ('printenv')
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
