pipeline {
  agent any
    stages {      
        stage('Build maven ') {
            steps { 
                    sh 'pwd'      
                    sh 'mvn  clean install package'
            }
        }
        
        stage('Copy Artifact') {
           steps { 
                   sh 'pwd'
		   sh 'cp -r webapp/target/*.war .'
           }
        }
         
        stage('Build docker image') {
           steps {
               script {         
                 def customImage = docker.build('mmravi99/helloworld02', ".")
                 docker.withRegistry('https://registry.hub.docker.com', 'mmr-docker') {
                 customImage.push("${env.BUILD_NUMBER}")
                 }                     
           }
        }
	  }
    }
}
