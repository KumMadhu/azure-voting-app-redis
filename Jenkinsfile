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
				sh '/Applications/Docker.app/Contents/Resources/bin/docker images -a'
				sh '''
					cd azure-vote/
					/Applications/Docker.app/Contents/Resources/bin/docker images -a
					/Applications/Docker.app/Contents/Resources/bin/docker build -t jenkins-pipeline .
					/Applications/Docker.app/Contents/Resources/bin/docker images -a
					cd ..
					'''
			}
		}
	}
}
