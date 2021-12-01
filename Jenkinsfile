pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
			    cleanWs()
				checkout scm
			}
		}
        stage('build')
        {
            steps{
                sh 'apt-get update'
            }
        }
		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
