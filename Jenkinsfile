//Scripted
//node {
//	stage('Build') {
//		echo "Build"
//	}
//	stage('Test') {
//		echo "Test"
//	}
//	stage('Integration Test') {
//		echo "Integration Test"
//	}
//}

//Declarative
pipeline{
	agent any//{ docker {image 'node:13.8'} }
	//agent { docker {image 'maven:3.6.3'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker --version'
				//sh 'node --version'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER- $env.BUILD_NUMBER"
				echo "BUILD_ID- $env.BUILD_ID"
				echo "JOB_NAME- $env.JOB_NAME"
				echo "BUILD_URL- $env.BUILD_URL"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	} 
	
	post{
		always {
			echo "I run always."
		}
		success {
			echo "Completed Successfully."
		}
		failure {
			echo "Issue found."
		}
		changed {
			echo "Build status changed."
		}
	}
}