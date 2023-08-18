pipeline {
	agent any
	// // agent{
	// // 	docker {
	// // 		image 'maven:3.6.3'
	// // 	}
	// // }
	// agent{
	// 		docker{
	// 			image 'node:13.8'
	// 		}
	// }

	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH : $PATH"
					echo "$env.BUILD_ID"
					echo "$env.BUILD_TAG"
			}
		}
		stage('Test'){
			steps{
					echo "Test"
			}
		}
		stage('IntegrationTest'){
			steps{
					echo "Integration test"
			}
		}
	} 
	
	post{
		always{
			echo "Cool!"
		}
		success{
			echo 'Successful message'
		}
		failure{
			echo "too bad"
		}
	}



}

