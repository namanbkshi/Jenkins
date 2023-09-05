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
                        attachments: '**/*.log'
                        
                    
                }
                failure {
                    mail to: "namanbakshi1@gmail.com",
                        subject: "Unit and Integration Tests have failed",
                        body: "Fail"
                        attachments: '**/*.log'
                    
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
                    mail to: "namanbakshi1@gmail.com",
                        subject: "Security scan is sucessful",
                        body: "Successful"
                        
                    
                }
                failure {
                    mail to: "namanbakshi1@gmail.com",
                        subject: "Security Scan failed",
                        body: "Fail"
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
