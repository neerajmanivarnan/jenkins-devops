pipeline {

	agent any

	stages{

		stage("Build"){
			steps{
				echo "This is the build stage" 
			}
		}

		stage("Test"){
			steps{
				echo "This is the test stage" 
			}
		}

		stage("QA"){
			steps{
				echo "This is the QA stage" 
			}
		}


		stage("Production"){
			steps{
				echo "This is the production stage" 
			}
		}
	}

	post{
		always{
			echo "This always runs"
		}

		success{
			echo "This only runs when this is script is success"
		}

		failure{
			echo "This runs only when the script fails to run"
		}
		

	}

}
