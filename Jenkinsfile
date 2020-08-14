pipeline {
	agent any
	stages {
	    stage('mvn build'){
	        steps {
	            sh 'mvn clean install package'
	        }
	    }
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