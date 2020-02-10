#!/usr/bin/groovy
pipeline {
	agent any

    options {
        disableConcurrentBuilds()
    }

	stages {

		stage('Build') {
			steps { buildApp()}
		}

		stage('Test') {
			steps {
				echo 'Testing..'
			}
		}

		stage('Deploy') {
			steps {
				echo 'Deploying....'
			}
		}

	}
}

// steps
def buildApp() {
	dir ('client' ) {
		def appImage = docker.build("jenkins/myapp-client:${BUILD_NUMBER}")
	}
}