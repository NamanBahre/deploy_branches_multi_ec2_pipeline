pipeline {
    agent {
        label "slave-1"
    }

    stages {
        stage('Build') {
            steps {
                
             //  sh "rm -rf /mnt/jenkins_slave1/workspace/*"
               sh "sudo yum install httpd git -y"
          
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git',branch:'Q1'
                
                sh "sudo cp -r /mnt/jenkins_slave1/workspace/test/*.html /var/www/html/"
                sh "sudo service httpd restart"
                
        
       
               
            
                
            }

            }
        }
    }
