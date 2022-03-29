pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{                
                sh 'ssh -i /home/ec2-user/bantu.pem ec2-user@3.110.204.121 -y'
                sh 'sudo su'
                sh 'yum update -y'
                sh 'amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2'
                sh 'yum install -y httpd mariadb-server'
                sh 'systemctl start httpd'
                sh 'systemctl enable httpd'
                sh 'usermod -a -G apache ec2-user'
                sh 'chown -R ec2-user:apache /var/www'
                sh 'chmod 2775 /var/www'
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
