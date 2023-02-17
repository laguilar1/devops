pipeline {

  environment {
    dockerImageName1 = "laguilar1/curso:devops"
    dockerImage1 = ""
    GITHUB_URL = "https://github.com/laguilar1/devops.git" // "$GITHUB_URL"
    CREDENTIAL_ID = "github-credential-laguilar1"         // "$CREDENTIAL_ID"
  }

  agent any
  stages {

    stage('Checkout Source') { 
      steps {
        git credentialsId: "${env.CREDENTIAL_ID}", url: "${env.GITHUB_URL}", branch:'main'
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