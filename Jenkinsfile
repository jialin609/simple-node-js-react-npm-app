pipeline {
  agent any
	stages {
		stage('Checkout SCM') {
			steps {
			    cleanWs()
				checkout scm
			}
		}
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }i}
