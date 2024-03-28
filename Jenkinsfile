pipeline {
	agent any

	environment {
		mavenHome = tool 'MAVEN_HOME'
	}

	tools {
		jdk 'java-17'
		maven 'MAVEN_HOME'
	}

	stages {

		stage('Build'){
			steps {
				sh "mvn clean install -DskipTests"
			}
		}

		stage('Test'){
			steps{
				sh "mvn test"
			}
		}

		stage('Deploy') {
			steps {
			    sh "mvn jar:jar deploy:deploy"
			}
		}
	}
}
