pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
	stage('Checkout'){
	steps{
		git branch:'master',url:'https://github.com/prxj10/mvn4.git'
	}
	}
	stage('Build'){
	steps{
		sh 'mvn clean install'
	}
	}
	stage('Prepare File'){
	steps{
		sh 'echo "Jenkins Data" > source.txt'
	}
	}
	stage('Run Application'){
	steps{
		sh 'java -jar target/mvn4-1.0-SNAPSHOT.jar'
	}
	}
	}
	post{
	success{
		echo 'Build successful!'
	}
	failure{
		echo 'Build failed!'
	}
	}
}
