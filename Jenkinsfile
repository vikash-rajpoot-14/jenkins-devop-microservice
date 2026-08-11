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
	stages {
		stage ('Build'){
			stpes {
              echo "Build"
			}
	       
		}
		stage ('Test'){
			stpes {
              echo "Test"
			}
		}
		stage ('Integration Test'){
			stpes {
              echo "Integration Test"
			}
		}
	}
}