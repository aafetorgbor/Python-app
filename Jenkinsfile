pipeline {
    agent any
    

    stages {
        
         stage('CHECKOUT CODE') {
            steps {
             
             checkout([$class: 'GitSCM', 
             branches: [[name: '*/main']],
             extensions: [],
             userRemoteConfigs: [[url: 'https://github.com/aafetorgbor/Python-app.git']]])
            }
        }
        
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
