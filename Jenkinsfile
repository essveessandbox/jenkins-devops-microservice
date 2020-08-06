//Scripted Pipeline (old way)
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test') {
// 		echo 'Integration Test'
// 	}
// }

//Declarative Style of setting up pipeline

pipeline {
	agent any
	stages 	{
		stage('Build'){
			steps {
				echo "Build"
			}
		}
		stage('Test'){
			steps {
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps {
				echo "Integration Test"
			}
		}
	} post {
		always {
			echo 'Im awesome. I run always'
		}
		success {
			echo 'I run when successful'
		}
		failure {
			echo 'I run when there is failure'
		}
	}
	
}