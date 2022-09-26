pipeline {
	agent any
    stages {
        stage('Build on k8 ') {
            steps {           
                        sh 'pwd'
                        sh 'cp -R helm/* .'
		        sh 'ls -ltr'
                        sh 'pwd'
		        sh 'aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 651308448971.dkr.ecr.ap-south-1.amazonaws.com'
                        sh '/usr/local/bin/helm upgrade --install petclinic-app petclinic  --set image.repository=651308448971.dkr.ecr.ap-south-1.amazonaws.com/javaapp --set image.tag=1'
              			
            }           
        }
    }
}
