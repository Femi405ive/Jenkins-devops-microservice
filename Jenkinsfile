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
			sh "mvn clean compile"
			}
		}

		stage('test') {
			steps {
			sh "mvn test"
			}
		}

		stage('integration test') {
			steps {
			sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
}
}