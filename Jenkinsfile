pipeline {
    agent {
        label "slave-3"
    }

    stages {

        stage ('install'){
            steps{                
               sh "sudo yum install httpd -y"
                sh "sudo yum install git -y"
            }
        }
        stage('Build') {
            steps {
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git',branch:'Q3'
                sh "sudo cp -r /mnt/jenkins_slave1/workspace/test/*.html /var/www/html/"
                sh "sudo service httpd restart"
                }
            }
        }
    }
