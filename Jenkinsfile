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
	        stage("Bring grid down")
	        {
                    steps{
                       sh "docker-compose down"
                    }
	        }
	    }
}
