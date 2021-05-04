pipeline {
	agent any

	stages {
		stage('Verify Branch'){
			steps {
				echo "$GIT_BRANCH"
				sh(script: 'echo Hello World')
			}
		}
		stage('Docker Build'){
			steps{
				sh 'docker images -a'
				sh '''
					cd azure-vote/
					docker images -a
					docker build -t jenkins-pipeline .
					docker images -a
					cd ..
					'''
			}
		}
	}
}
