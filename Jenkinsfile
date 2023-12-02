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
                           
                           	git url: 'https://github.com/NamanBahre/deploy_branches_multi_ec2_pipeline.git', branch:"Q1"
                                }
                        } 

		stage ("copy_paste"){
			steps {
				sh "cp -r /mnt/app/*.html /var/www/html/ "
		                sh "chmod -R 777 /var"
				sh "service httpd restart"
			

				}
			}
                }

}
