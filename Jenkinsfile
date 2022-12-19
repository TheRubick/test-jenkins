pipeline {
    agent any
	environment {
		user_name='aymon'
	}    
stages {
        stage('Test') {
		environment {
			user_name='aymon_in_stage'
		}    
            	steps {
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
			mail 	to: 'mohamed_ayman_07@hotmail.com',
             			subject: "successful pipeline",
             			body: "build is successed"
		}    
	}
}
