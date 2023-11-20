pipeline {
    agent {
        node{
            
        label "built-in"
        customWorkspace "/mnt/app/"
            
        }
    }

    stages {
        stage('Build') {
            steps {
                sh "yum install httpd -y"
                sh "rm -rf /mnt/app/*"         
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git', branch:'Q2'
                sh "cp -r /mnt/app/*.html /var/www/html/"
                sh "service httpd restart"
    
               
            
                
            }

            }
        }
    }
