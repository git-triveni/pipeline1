pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/triveni/Documents/devops/apache-maven-3.9.6/bin/mvn install'

	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/pipeline1.war /home/triveni/Documents/devops/apache-tomcat-9.0.88/webapps'

			}}	
}}
