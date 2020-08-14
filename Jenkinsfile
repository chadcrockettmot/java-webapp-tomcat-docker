pipeline {
	agent any
	stages {
	    stage('Docker image build'){
	        steps {
	            sh 'docker build -t travelblog .'
	        }
	    }
	    stage('Run Docker Container'){
	        steps{
	            sh 'docker container run --rm --name tbcontainer -p 8000:8080 -d travelblog'
	        }
	    }
	}
}