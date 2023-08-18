pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
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

