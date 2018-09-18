pipeline {
	agent any 
	stages {
		stage('Build') {
			steps {
				sh 'mvn clean package'
			}
		}
		stage('Archive') {
			steps {
				post {
					success {
						echo 'Now archiving'
						archiveArtifacts artifacts: '**/target/*.war'
					}
				}
			}
		}
	}
}