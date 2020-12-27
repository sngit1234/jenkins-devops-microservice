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
	agent { docker {image 'maven:3.6.3'} }
	stages {
		stage('Build'){
			steps{
				sh 'mvn --version'
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