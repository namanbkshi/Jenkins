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
            post {
                success {
                    mail to: "namanbakshi1@gmail.com",
                        subject: "Unit and Integration Tests are succesful",
                        body: "Successful"
                        
                    
                }
                failure {
                    mail to: "namanbakshi1@gmail.com",
                        subject: "Unit and Integration Tests have failed",
                        body: "Fail"
                    
                }
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
            post {
                success {
                    emailext subject: 'Security Scan - Success',
                              body: 'Security Scan has passed successfully.',
                              to: 'namanbakshi1@gmail.com',
                              attachLog: true
                }
                failure {
                    emailext subject: 'Security Scan - Failure',
                              body: 'Security Scan has failed.',
                              to: 'namanbakshi1@gmail.com',
                              attachLog: true
                }
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
}
