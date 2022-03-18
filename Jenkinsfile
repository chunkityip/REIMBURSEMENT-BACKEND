pipeline {
	agent any
	stages {
		stage ('Clone Code') {
			steps {
				git branch: 'main', url: 'git@github.com:ckyrevature/REIMBURSEMENT-BACKEND'
			}
		}
		
		stage ('Build Code') {
			steps {
				sh 'mvn clean package'
			}
		}
		
		stage ('Staging') {
			steps {
				sh 'docker-compose down'
				sh 'docker-compose up -d'
			}
		}
	}