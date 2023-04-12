pipeline {
    agent any
	environment {
		user_name='aymon'
	}    
stages {
	stage('Build') {
            	steps {
                	sh 'echo "building stage is here"'
            	testChangingThePath()
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
		}    
	}
}

def testChangingThePath(){
  dir("./section_4/")
  {
      sh "echo I am here `pwd`"
  }
}
