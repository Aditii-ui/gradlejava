pipeline {
    agent any 
    tools {
        gradle 'MyGradleApp'
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Aditii-ui/gradlejava.git'
            }
        }
        stage('Build') {
            steps {
                sh 'gradle build'
            }
        }
       stage('Test') {
           steps {
               sh 'gradle test' 
           }
        }     
        stage('Run Application') {
            steps {
                sh 'gradle run'
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

