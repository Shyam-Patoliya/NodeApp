pipeline {
	agent any
	tools {
		nodejs 'NodeJS'
	}
	
	stages {
		stage('Checkout Github'){
			steps {
				git branch: 'main', credentialsId: 'jen-doc-git', url: 'https://github.com/Shyam-Patoliya/NodeApp.git'
			}
		}		
		stage('Install node dependencies'){
			steps {
				sh 'npm install'
			}
		}
		stage('Test Code'){
			steps {
				sh 'npm test'
			}
		}
		
	post {
		success {
			echo 'Build&Deploy completed succesfully!'
		}
		failure {
			echo 'Build&Deploy failed. Check logs.'
		}
	}
}
