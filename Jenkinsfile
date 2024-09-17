pipeline {

    agent any

	environment{
		mavenHome = tool "maven-cli"
		dockerHome = tool "docker-plugin"
		PATH = "$mavenHome/bin:$dockerHome/bin:$PATH"
	}


    stages {

        stage("Build") {
            steps {
	    	sh 'mvn --version'
	    	sh 'docker version'
		echo "Default path - $env.PATH"
		echo "Build number - $env.BUILD_NUMBER"
		echo "Build ID - $env.BUILD_ID"
		echo "Job name - $env.JOB_NAME"
            }
        }

        stage("Test") {
            steps {
                echo 'This is the Test stage'
            }
        }

        stage("QA") {
            steps {
                echo 'This is the QA stage'
            }
        }

        stage("Prod") {
            steps {
                echo 'This is the Prod stage'
            }
        }

    }

}

