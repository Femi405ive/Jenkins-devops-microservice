pipeline {
	agent any 
	// agent {docker { image 'node:13.8'}}
	environment {
		dockerHome  = tool 'myDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('checkout') {
			steps {
			sh 'mvn --version'
			sh 'docker version'
			echo "build"
			echo "path - $path"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			echo "BUILD_ID - $env.BUILD_ID"
			echo "JOD_NAME - $env.JOD_NAME"
			echo "BUILD_TAG - $env.BUILD_TAG"
			}
		}
		stage('Compile') {
			steps {
			echo "mvn clean compile"
			}


		stage('test') {
			steps {
			echo "mvn test"
			}
		}

		stage('integration test') {
			steps {
			echo "mvn failsafe:integration-test failsafe:verify"
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
}