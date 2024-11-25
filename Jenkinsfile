pipeline {
	agent any
	enviornment {
		DOCKER_IMAGE = 'hello-world-java:latest'  //Docker image name
	}
	stages {
		stage('checkout') {
			steps {
				checkout scm
			      }
		}
		stage('build') {
			steps {
			  sh 'javac HelloWorld.java'
			}
		}
		stage('package') {
			steps {
			  sh 'jar cf HelloWorld.jar HelloWorld.class'
				}
		}
		stage('Docker Build') {
			steps {
			  sh """
			  docker build -t $DOCKER_IMAGE .
			  """
			}
		}
	post {
		success {

			echo 'buiild successfully'
			}
		failure {
			echo 'build failed'
			}
	     }
	}
	
}
		 
			
