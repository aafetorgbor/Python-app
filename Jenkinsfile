pipeline {
   agent any
    
    stages {
       
         stage('BUILD') {
             when {
                  allOf {
                  expression { env.BRANCH_NAME == "origin/master" }
                  expression { params.merged == true }
                  expression { params.current_status == "closed" }
                        }
                 }
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
    
       post('Slack notificion sent'){
            always{
               cleanWs()
            }
        }
    
}
