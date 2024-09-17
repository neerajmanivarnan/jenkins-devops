pipeline {

    agent any

	environment{
		mavenHome = tool "maven-cli"
		dockerHome = tool "docker-plugin"
		PATH = "$mavenHome/bin:$dockerHome/bin:$PATH"
	}


    stages {

        stage("checkout") {
            steps {
	    	sh 'mvn --version'
	    	sh 'docker version'
		echo "Default path - $env.PATH"
		echo "Build number - $env.BUILD_NUMBER"
		echo "Build ID - $env.BUILD_ID"
		echo "Job name - $env.JOB_NAME"
            }
        }

        stage("Compile") {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage("Test") {
            steps {
                sh 'mvn test'
            }
        }

        stage("Integration test") {
            steps {
                sh "mvn failsafe:integration-test failsafe:verify"
            }
        }

    }

}

