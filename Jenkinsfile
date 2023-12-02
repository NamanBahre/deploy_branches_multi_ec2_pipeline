pipeline {
    agent {
        label "slave-1"
        customWorkspace "/mnt/app"
    }

    stages {

        stage ('install'){
            steps{   
                sh "chmod -R 777 /mnt"
               sh "sudo yum install httpd -y"
                sh "sudo yum install git -y
        }
        stage('Build') {
            steps {
                git url:'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git',branch:'Q1'
                sh "sudo cp -r /mnt/jenkins_slave1/workspace/test/*.html /var/www/html/"
                sh "chmod -R 777 /var"
                sh "sudo service httpd restart"
                }
            }
        }
    }
