pipeline {
    agent { dockerfile true}
    

    stages {
        
     
         stage('BUILD') {
            steps {
               
               echo 'Building...' 
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
