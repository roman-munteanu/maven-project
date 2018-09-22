pipeline {
	agent any 
	stages {
		stage('Build') {
			steps {
				bat 'mvn clean package'
				bat "docker build . -t tomcatwebapp:${env.BUILD_ID}"
			}
			post {
				success {
					echo 'Now archiving'
					archiveArtifacts artifacts: '**/target/*.war'
				}
			}
		}
	}
}
