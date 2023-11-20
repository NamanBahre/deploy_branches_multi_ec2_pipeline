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
          
                git 'https://github.com/NamanBahre/project.git'

                sh "mvn clean install"
                
                sh "cp -r /mnt/app/target/*.war /mnt/servers/apache-tomcat-9.0.82/webapps"
    
               
            
                
            }

            }
        }
    }
