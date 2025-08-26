pipeline {
   agent any

   environment{
      DEPLOYMENT_MAIN = "N8N"
      DEPLOYMENT_WORKER = "N8N-WORKER"
      CLUSTER = "XFLOW"
   }
    
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
             echo "Deploying to $DEPLOYMENT_MAIN"

             elif [[ "${GIT_BRANCH#origin/}" == "test" ]]; then
             NAMESPACE=n8n-test
             echo "Deploying to $NAMESPACE"
             echo "Deploying to $DEPLOYMENT_WORKER"

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

