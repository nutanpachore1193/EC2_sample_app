pipeline {
    agent any

    stages{
        stage('deploy to ec2'){
            steps{        
                sh 'cp index.html /var/www/html/'
                
            }
        }
    }
    post{
        always{
            cleanWs disableDeferredWipeout: true, deleteDirs: true
        }
    }

}
