pipeline {
    agent any
	environment {
		user_name='aymon'
	}    
stages {
	stage('Build') {
            	steps {
            	buildTheApp()
            }
        }
        stage('Test') {
		environment {
			user_name='aymon_in_stage'
		}    
  steps {
			      input "do you want to proceed?"
            sh 'ls -l'
			      sh 'echo "now the user name = ${user_name}"'
        }
      }	
    }
   	post {
		always
		{
			echo "this will be always printed"
		}
		success
		{
			echo "build has been successed"
      sh "docker rmi web-app-jenkins:${BUILD_NUMBER}"
		}    
	}
}

def buildTheApp(){
  dir("./section_4/code/cd_pipeline")
  {
      docker.build("web-app-jenkins:${BUILD_NUMBER}")
  }
}
