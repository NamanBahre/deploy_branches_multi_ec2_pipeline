pipeline {
    agent {
        label "slave-3"
    }

    stages {
        stage('Build') {
            steps {
                
               sh "sudo yum install httpd git -y"
          
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git',branch:'Q3'
                
                sh "sudo cp -r /mnt/jenkins_slave1/workspace/test/*.html /var/www/html/"
                sh "sudo service httpd restart"
                
        
       
               
            
                
            }

            }
        }
    }
