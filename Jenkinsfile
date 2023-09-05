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
        always {
            script {
                currentBuild.result = 'SUCCESS'
                if (currentBuild.currentResultIsWorseThan(Result.SUCCESS)) {
                    currentBuild.result = 'FAILURE'
                }
            }
        }
        failure {        
            emailext subject: "Pipeline Failed - ${currentBuild.result}",
                body: 'The Jenkins pipeline has failed. Please check the logs for details.',
                to: 'namanbakshi1@gmail.com',
                attachmentsPattern: '**/build.log'
        }
        success {
            emailext subject: "Pipeline Successful - ${currentBuild.result}",
                body: 'The Jenkins pipeline has completed successfully.',
                to: 'namanbakshi1@gmail.com',
                attachmentsPattern: '**/build.log'
        }
    }
}
