pipeline {

    agent any

    environment {
        mavenHome = tool "maven-cli"
        dockerHome = tool "docker-plugin"
        PATH = "$mavenHome/bin:$dockerHome/bin:$PATH"
    }

    stages {

        stage("Checkout") {
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
                echo "This is the compile stage"
            }
        }

        stage("Test") {
            steps {
                echo "This is the test stage"
            }
        }

        stage("Integration Test") {
            steps {
                echo "This is the integration test stage"
            }
        }

        stage("Docker Build") {
            steps {
                script {
                    dockerImage = docker.build("neergasm/azure-devops-build-and-push:${env.BUILD_ID}")
                }
            }
        }

        stage("Docker Push") {
            steps {
                script {
                    docker.withRegistry('', 'dockerhub') {
                        dockerImage.push()
                        dockerImage.push('latest')
                    }
                }
            }
        }
    }
}

