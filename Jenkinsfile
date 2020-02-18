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
		def appImageProd = docker.build("jenkins/myapp-client_prod:${BUILD_NUMBER}", "-f Dockerfile.prod .")
	}
	
	dir ('server' ) {
		def appImage = docker.build("jenkins/myapp-server:${BUILD_NUMBER}")
		def appImageProd = docker.build("jenkins/myapp-server_prod:${BUILD_NUMBER}", "-f Dockerfile.prod .")
	}
}
