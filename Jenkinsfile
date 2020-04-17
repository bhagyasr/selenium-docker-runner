pipeline{
	agent any
	    stages{
	        stage("Start Grid"){
	            steps{
	               sh "docker-compose up -d hub hub chrome firefox"
	            }
	        }
		stage("Running Tests"){
	            steps{
	               sh "docker-compose up searchmodule bookflightmodule"
	            }
	        }
	    }
	post {
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
		}
	}
}
