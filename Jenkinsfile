pipeline {
	agent any
    stages {
        stage('Build on AKS ') {
            steps {           
                        sh 'pwd'
                        sh 'cp -R helm/* .'
		        sh 'ls -ltr'
                        sh 'pwd'
                        sh '/usr/local/bin/helm upgrade --install helloworld hello-world'
              			
            }           
        }
    }
}
