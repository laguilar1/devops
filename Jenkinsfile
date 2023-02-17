pipeline {

  environment {
    dockerImageName1 = "laguilar1/curso:devops"
    dockerImage1 = ""
    urlRepo = "https://github.com/laguilar1/devops.git"
    credentialId = "github-credential-laguilar1"
  }

  agent any
  stages {

    stage('Checkout Source') { 
      steps {
        git credentialsId: credentialId, url: urlRepo, branch:'main'
      }
    }
    stage('Construir Imagen Aplicación') {
	    steps{
	      dir('proyecto'){
	        script {
            dockerImage1 = docker.build dockerImageName1
          }
        }
      }
    }
  }

}