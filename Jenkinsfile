// SCRIPTED PIPELINE APPROACH
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage ("Integration Test") {
// 		echo "Integration Test"
// 	}
// }
// still correct
// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Integration Test"
// }


// DECLARATIVE PIPELINE

pipeline {
	agent { docker { image 'maven:3.6.3'} }
	stages {
		stage ('Build'){
			steps {
			  sh 'mvn --version'
              echo "Build"
			}
	       
		}
		stage ('Test'){
			steps {
              echo "Test"
			}
		}
		stage ('Integration Test'){
			steps {
              echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo "i am awesome. i run always"
		}
		success {
			echo "i run when u are successful"
		}
		failure {
			echo "i run when u failed"
		}
		//changed and unstable two more methods
	}
}