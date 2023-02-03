pipeline {
	// agent any 
	agent {docker { image 'maven:3.6.3'}}
	stages {
		stage('build') {
			steps {
			echo"build"
			}
		}
		stage('test') {
			steps {
			echo "test"
			sh 'mvn --version'
			}
		}

		stage('integration test') {
			steps {
			echo "integration test"
			}
		}
	}
	post {
		failure {
			echo "i failed i am sorry about that. try again"
		}
	
	always {
			echo "yay i run always" 
		}
	
		success {
			echo "i told you i was going to make it"
		}
	}
}
