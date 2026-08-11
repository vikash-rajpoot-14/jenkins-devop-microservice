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
	agent any
	// agent { docker { image 'maven:3.6.3'} }
	// agent { docker { image 'node:13.8'} }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
        PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout'){
			steps {
			  sh 'mvn --version'
			  sh 'docker --version'
              echo "Build"
			  echo "$PATH"
			  echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			  echo "BUILD_ID - $env.BUILD_ID"
			  echo "JOB_NAME - $env.JOB_NAME"
			  echo "BUILD_TAG - $env.BUILD_TAG"
			  echo "BUILD_URL - $env.BUILD_URL"
			}
	       
		}
		stage ('Compile'){
			steps {
              sh "mvn clean compile"
			}
		}
		stage ('Test'){
			steps {
              sh "mvn test"
			}
		}
		stage ('Integration Test'){
			steps {
              sh "mvn failsafe:integration-test failsafe:verify"
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