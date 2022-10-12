pipeline {
    agent any
    environment{
        DOCKERHUB_CREDS = credentials('DockerHub')
    }
    stages {
        stage('Clone Repo') {
            steps {
                checkout scm
                sh 'ls *'
            }
        }
        stage('Build Image') {
            steps {
		    script{
			    sh 'docker build -t callmejaja/pipeline:$BUILD_NUMBER .'
		    }
            }
        }
        
    post {
		always {
			sh 'docker logout'
		}
	 }
    }

