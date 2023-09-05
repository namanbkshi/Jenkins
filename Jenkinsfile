pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build Automation Tool: Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Unit Testing Tool: JUnit'
                echo 'Integration Testing Tool: TestNG'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Code Analysis Tool: SonarQube'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security Scanning Tool: OWASP ZAP'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deployment Tool: AWS CodeDeploy'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration Testing Tool (on staging): Selenium'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deployment Tool: AWS CodeDeploy'
            }
        }
    }
    post {
        success {           
            emailext subject: 'Pipeline Successful',
                body: 'The Jenkins pipeline has success.',
                to: 'namanbakshi1@gmail.com',
                
        }
        failure {           
            emailext subject: 'Pipeline Failed',
                body: 'The Jenkins pipeline failed.',
                to: 'namanbakshi1@gmail.com',
                
        }
    }
}
