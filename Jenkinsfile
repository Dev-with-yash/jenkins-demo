pipeline{
	agent any
	stages{

		stage('Checkout'){
			steps{

				git branch: 'dev', url: 'https://github.com/Dev-with-yash/jenkins-demo.git'
			}

		}
		stage('Change Dir'){
			steps{
                dir('jerkins-demo2') {
                       	bat 'mvn clean compile'
                       	bat 'mvn test'
}
			
			}

		}
		
	
		stage('Report'){
			steps{

				bat 'echo junit tests are done'
			}

		}

	}
	post{

		always{
			archiveArtifacts artifacts:'**/target/*.jar', allowEmptyArchive:true
		
		}
		failure{
				mail to: 'akasamyaswanth1@outlook.com',
				     subject:"success", 
			             body: "build is successful"

		}
		
	}
