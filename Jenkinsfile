pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	environment {
        DOCKER_HOST = 'unix:///var/run/docker.sock'
    }
	stages {
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}
