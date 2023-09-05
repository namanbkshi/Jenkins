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
                    emailext subject: 'Unit and Integration Tests - Success',
                              body: 'Unit and Integration Tests have passed successfully.',
                              to: 'namanbakshi1@gmail.com',
                              attachLog: true
                }
                failure {
                    emailext subject: 'Unit and Integration Tests - Failure',
                              body: 'Unit and Integration Tests have failed.',
                              to: 'namanbakshi1@gmail.com',
                              attachLog: true
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
