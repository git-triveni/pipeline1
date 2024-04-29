
pipeline {
	agent any
	
	parameters {
		choice(name: 'ENV', choices: ['QA','UAT'], description: 'Pick Env value')
	}
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
			script {
			 if ( env.ENV == 'QA' ){
        	sh 'cp target/pipeline1.war /home/triveni/Documents/devops/apache-tomcat-9.0.88/webapps '

        	echo "deployment has been done on QA!"
			 }
			else ( env.ENV == 'UAT' ){
    		sh 'cp target/pipeline1.war /home/triveni/Documents/devops/apache-tomcat-9.0.88/webapps '

    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			}}}
		stage('slack'){
			steps{
				slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'grras1', color: 'good', message: 'hello slack', teamDomain: 'DEVOPS', tokenCredentialId: 'anything'
			}}
}}
