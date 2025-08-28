pipeline {
	//agent { docker { image 'maven:3.9.11'} }
	agent any

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				bat "mvn --version"
				bat "docker version"
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"

			}
		}	
		stage('Test') {
			steps {
				echo "Test"
			}
		}	
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
		
	} 

	post {
		always {
			echo 'I run always'
		}
		success {
			echo 'I run when you are successful'
		}
		failure {
			echo 'I run when you fail'
		}
	}	


	stage('Validate') {
            steps {
                script {
                    bat 'ls -la'
                }
            }
}
