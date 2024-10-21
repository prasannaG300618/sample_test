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
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        // Add more stages here (e.g., Deploy, PublishArtifacts)
    }
    
    post {
        always {
            // Send clean-up email notification
            emailext(
                subject: "Jenkins Job - Cleanup",
                body: "The job has completed and the system is cleaning up.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
        
        success {
            // Send success notification
            emailext(
                subject: "Jenkins Job - SUCCESS",
                body: "Great news! The job was successful.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
        
        failure {
            // Send failure notification
            emailext(
                subject: "Jenkins Job - FAILURE",
                body: "Unfortunately, the job has failed. Please check the logs.",
                to: 'prasannakithiyon53@gmail.com'
            )
        }
    }
}
