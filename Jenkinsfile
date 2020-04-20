pipeline{
	agent any
	    stages{
		 stage("Pull Latest Image from docker hub"){
	            steps{
	               sh "docker pull bhagyan/selenium-docker:latest"
	            }
	        }
	        stage("Start Grid"){
	            steps{
	               sh "docker-compose up -d hub chrome firefox"
	            }
	        }
		stage("Running Tests"){
	            steps{
	               sh "docker-compose up searchmodule bookflightmodule"
	            }
	        }
	    }
	 post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	    }
}
