pipeline {
	// agent any
	// agent{
	// 	docker {
	// 		image 'maven:3.6.3'
	// 	}
	// }
	agent{
		image{
			docker{
				image 'node:13.8'
			}
		}
	}
	stages{
		stage('Build'){
			steps{
					// sh 'mvn --version'
					sh 'node --version'
					echo "Build"
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

