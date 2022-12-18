pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'ls -l'
            }
        }
    }
   	post {
		always
		{
			echo "this will be always printed"
		}    
	}
}
