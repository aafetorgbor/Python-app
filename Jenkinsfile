pipeline {
   agent any
    
    stages {
       
         stage('BUILD') {
            steps {
               sh '''
               pytest -v
              # echo " Branch: $GIT_BRANCH"
               # echo "Branch: $GIT_LOCAL_BRANCH"

                 echo ${GIT_BRANCH#origin/}
              '''
               
       
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
