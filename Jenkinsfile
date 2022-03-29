node {
    stage ('Git')
    {
        git 'https://github.com/kaustubhchandra/ec2-project.git'
    }
    
    stage ('Build')
           {
               sh 'rsync -avrh index.html root@3.110.204.121:/var/www/html/'
            
           }

    }
