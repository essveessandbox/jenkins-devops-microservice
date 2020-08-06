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
	// agent {docker {image 'maven:3.6.3'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		path = "$dockerHome:/bin:$mavenHome/bin:$PATH"
	}
	stages 	{
		stage('Permissions') {
            steps {
                sh 'chmod 775 *'
            }
		}
		stage('Build'){
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD URL - $env.BUILD_URL"
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
	} 
	post {
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