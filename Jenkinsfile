pipeline {
	agent{
	label 'mens-slave'
	}
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/grras/appfiles/apache-maven-3.9.6/bin/mvn install'
	                 }}
		steps {
			sh 'cp target/Netflix6.war /home/grras/appfiles/apache-tomcat-9.0.85'
			}}
			
}
