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
		stage('Checkout'){
			steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH : $PATH"
					echo "$env.BUILD_ID"
					echo "$env.BUILD_TAG"
			}
		}

		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
					sh "mvn Test"
			}
		}
		stage('Integration Test'){
			steps{
					sh "mvn failsafe:integration-test failsafe:verify"
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

