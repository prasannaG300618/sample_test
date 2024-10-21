pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/prasannaG300618/sample_test.git'
            }
        }
        
        stage('Build') {
            steps {
                bat 'mvn clean package'  // Use 'bat' for Windows
            }
        }
        
        stage('Test') {
            steps {
                bat 'mvn test'  // Use 'bat' for Windows
            }
        }
    }
    
    post {
        always {
            emailext(
                subject: "Jenkins Job - Cleanup",
                body: "The job has completed and the system is cleaning up.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
        
        success {
            emailext(
                subject: "Jenkins Job - SUCCESS",
                body: "Great news! The job was successful.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
        
        failure {
            emailext(
                subject: "Jenkins Job - FAILURE",
                body: "Unfortunately, the job has failed. Please check the logs.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
    }
}
