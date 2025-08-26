pipeline {
   agent any
    
    stages {
       
         stage('BUILD') {
            steps {
               sh '''
               pytest -v
             # echo ${GIT_BRANCH#origin/} 
             #echo ${GIT_BRANCH} 
               
              '''
            }
        }
        
     
        
         stage('DEPLOY') {
            steps {
                sh '''#!/bin/bash
              set  -e
             
             if [[ "${GIT_BRANCH#origin/}" == "dev" ]]; then
             NAMESPACE=n8n-dev
             echo "Deploying to $NAMESPACE"

             elif [[ "${GIT_BRANCH#origin/}" == "test" ]]; then
             NAMESPACE=n8n-test
             echo "Deploying to $NAMESPACE"

             else
              echo "Branch ${GIT_BRANCH#origin/} does not trigger a deployment"

            fi
               
              '''
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


