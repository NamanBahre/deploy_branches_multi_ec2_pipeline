pipeline{

        agent {
                node {
                        label "slave-1"
                    customWorkspace "/mnt/app/"
                        }
                }
    

        stages {
                stage ("delete"){
			steps {
			sh "cd /mnt/app/"
			sh "rm -rf *"	
			} 
			}
            stage ("install"){
			steps {
			 sh 'sudo yum install git -y'
             		 sh 'sudo yum install httpd -y'   
			} 
			}
			

		stage ("github repo") {
                        steps {
                           sh "git clone https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git -b Q1"
                                }
                        } 

		stage ("copy_paste"){
			steps {
				sh "sudo cp -r /mnt/app/deploy_branches_multi_ec2_pipeline/*.html /var/www/html/ "
                sh "sudo chmod -R 777 /var"
                sh "sudo service httpd restart"
			

				}
			}
                }

}
