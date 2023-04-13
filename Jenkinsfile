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
        stage('run the app') {
		environment {
			user_name='aymon_in_stage'
		}    
  steps {
            sh 'echo you are running the app now'
            runTheApp()
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
      sh "docker ps -f name=webapp -q | xargs -r docker stop"
      sh "docker ps -f name=webapp -qa | xargs -r docker rm"
      sh "docker rmi web-app-jenkins:${BUILD_NUMBER}"
		}
		success
		{
			echo "build has been successed"
		}    
	}
}

def buildTheApp(){
  dir("./section_4/code/cd_pipeline")
  {
      docker.build("web-app-jenkins:${BUILD_NUMBER}")
  }
}

def runTheApp(){
  sh "docker ps -f name=webapp -q | xargs -r docker stop"
  sh "docker ps -f name=webapp -qa | xargs -r docker rm"
  sh "docker run -d --name=webapp -p 5020:5000 web-app-jenkins:${BUILD_NUMBER}" 
}
