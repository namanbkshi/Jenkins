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
                    emailext subject: "Unit and Integration Tests are successful",
                        body: "Successful",
                        to: "namanbakshi1@gmail.com",
                        attachLog: true  // Attach build log to email
                }
                failure {
                    emailext subject: "Unit and Integration Tests have failed",
                        body: "Fail",
                        to: "namanbakshi1@gmail.com",
                        attachLog: true  // Attach build log to email
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
