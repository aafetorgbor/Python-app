pipeline {
    agent { dockerfile true}
    

    stages {
        
     
         stage('BUILD') {
            steps {
               
               echo 'Building...' 
                sh 'node --version'
                sh 'svn --version'
            }
        }
        
         
        
    }
    
    post('slack notificion sent'){
        always{
            cleanWs()
            }
        }
}
