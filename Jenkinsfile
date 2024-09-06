pipeline {

	agent any 

	stages{

		stage("Build"){
			steps{
				sh 'systemctl start docker'
				echo "This runs on ubuntu latest" 
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
			echo "This statement has been added after renovating the bash git script"
		}

		success{
			echo "This only runs when this is script is success"
		}

		failure{
			echo "This runs only when the script fails to run"
		}
		

	}

}
