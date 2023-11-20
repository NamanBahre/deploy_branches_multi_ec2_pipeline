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
                sh "rm -rf /mnt/app/*"
                sh "chmod -R 777 /mnt"
          
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git', branch:'Q1'
                
                sshagent(['slave']) {
                 sh "yum install httpd -y"  
                 sh "chmod -R 777 /var/www/html"   
                 sh "ssh -o StrictHostKeyChecking=no ec2-user@172.31.35.207 "
                 sh "scp /mnt/app/*.html ec2-user@172.31.35.207:/var/www/html"            
                 sh "service httpd restart"
                }
            
            }
        }
    }
}
