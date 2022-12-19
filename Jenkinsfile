pipeline {
    agent any
	environment {
		user_name='aymon'
	}    
stages {
        stage('build') {
		environment {
			user_name='aymon_in_stage'
		}    
            	steps {
                	sh 'ls -l'
			sh 'echo "user name = ${user_name}"'
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
			echo "build is successed"
		}    
	}
}
