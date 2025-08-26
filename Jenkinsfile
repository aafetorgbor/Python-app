pipeline {
   agent any
    
    stages {
       
         stage('BUILD') {
            steps {
               sh 'pytest -v'
              sh ' echo ${GIT_BRANCH#origin/} '

               sh ' echo ${GIT_BRANCH} '
       
            }
        }
        
     
        
         stage('DEPLOY') {
            steps {
                echo 'Deploying...'

               echo ' "${GIT_BRANCH}" '
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
