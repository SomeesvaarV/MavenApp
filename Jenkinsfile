pipeline{
	agent any
	tools{
		maven 'Maven'
		jdk 'JDK'
	}
	stages{
	
		stage('Checkout'){
			steps{
				git branch:'main', url:'https://github.com/SomeesvaarV/MavenApp.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'	
			}
		}
		stage('test'){
			steps{
				sh 'mvn test'	
			}
		}
		stage('Run'){
			steps{
				sh 'java -jar target/MavenApp-1.0-SNAPSHOT'	
			}
		}
	}
	
	post{
		success{
			echo 'Build and deployment successful'
		}
		failure{
			echo 'build failed'
		}
	}
}
