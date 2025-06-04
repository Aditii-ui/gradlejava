pipeline{
	agent any{
		environment{
			LANG='en_US.UTF-8'
			LC_ALL='en_US.UTF-8'
		}
		tools{
			gradle'Gradle'
		}
		stages{
			stage('Checkout'){
				steps{
					git branch:'master',url:'https://github.com/Aditii-ui/gradlejava.git'
				}
			}
			stage('Build'){
				steps{
					sh 'gradle build'
				}
			}
			stage('Test') {
            			steps {
                			sh 'mvn test' 
            			}
        		}       
        		stage('Run Application') {
            			steps {
                			sh 'java -jar target/gradle-1.0-SNAPSHOT.jar'
            			}
        		}        
    		}
    	post {
        	success {
            		echo 'Build and deployment successful!'
        	}
        	failure {
            		echo 'Build failed!'
        	}
    	}
}	
