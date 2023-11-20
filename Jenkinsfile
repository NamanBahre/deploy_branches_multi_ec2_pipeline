pipeline {
    agent {
        label "slave-2"
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
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git',branch:'Q2'
                sh "sudo cp -r /mnt/jenkins_slave/workspace/test/*.html /var/www/html/"
                sh "sudo service httpd restart"
                }
            }
        }
    }
