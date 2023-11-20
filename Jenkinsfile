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
          
                git url: 'https://github.com/NamanBahre/project.git'

                sh "mvn clean install"
                
        
        sshagent(['slave']) {
    // some block
                 sh "ssh -o StrictHostKeyChecking=no ec2-user@172.31.35.207 "
                
                sh "scp /mnt/app/target/LoginWebApp.war ec2-user@172.31.35.207:/mnt/servers/apache-tomcat-9.0.83/webapps/"
                    }
      
               
            
                
            }

            }
        }
    }
