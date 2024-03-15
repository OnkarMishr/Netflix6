pipeline {
    agent {
        label 'mens-slave'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    try {
                        sh '/home/onkar/Documents/Devops_Softawre/apache-maven-3.9.6/bin/mvn install'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error("Build failed: ${e.message}")
                    }
                }
            }
        }
        stage('Deployment') {
            steps {
                script {
                    try {
                        sh 'cp target/Netflix6.war /home/onkar/Documents/Devops_Softawre/apache-tomcat-9.0.85/webapps'
                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        error("Deployment failed: ${e.message}")
                    }
                }
            }
        }
    }
}
