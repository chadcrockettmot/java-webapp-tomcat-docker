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
	    stage('Stop running Container'){
	        steps {
	            sh 'docker stop $(docker ps -aq)'
	        }
	    }
	    stage('Remove running Container'){
	        steps {
	            sh 'docker rm $(docker ps -aq)'
	        }
	    }
	    stage('Run Docker Container'){
	        steps{
	            sh 'docker container run --name tbcontainer -p 8000:8080 -d travelblog'
	        }
	    }
	}
}