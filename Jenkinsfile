pipeline {
    agent { docker image 'qnib/pytest:latest'}
    

    stages {
        
     
         stage('BUILD') {
            steps {
               
               echo 'Building...' 
                
                
            }
        }
        
        stage('TEST'){
            steps{
            
                sh 'pytest -v'
            }
        }
        
        
         
        
    }
    
    post('slack notificion sent'){
        always{
            cleanWs()
            }
        }
}
