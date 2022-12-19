pipeline {
    agent any
	environment {
		user_name='aymon'
	}    
stages {
	stage('Build') {
            	steps {
                	sh 'echo "building stage is here"'
            	}
        }
        stage('Test') {
		environment {
			user_name='aymon_in_stage'
		}    
            	steps {
			input "do you want to proceed?"
                	sh 'ls -l'
			sh 'echo "testingggggggg"'
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
