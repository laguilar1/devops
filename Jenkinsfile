pipeline {
  agent any
  environment {
    dockerImageName1 = "laguilar1/curso:devops"
    dockerImage1 = ""
    GITHUB_URL = "https://github.com/laguilar1/devops.git"
    credentialId = "github-credential-laguilar1"
  }
  stages {

    stage('Checkout Source') { 
      steps {
        git credentialsId: 'github-credential-laguilar1', url: "$GITHUB_URL", branch:'main'
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