pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests using JUnit and integration tests using Selenium"
            }
            post{
                success {
                    emailext (to: "chanshut@gmail.com",
                    subject: "Unit and Integration Tests Status",
                    body: "Unit and Integration Tests were successful!",
                    attachLog: true)
                }
                failure {
                    emailext (to: "chanshut@gmail.com",
                    subject: "Unit and Integration Tests Status",
                    body: "Unit and Integration Tests were failed :(",
                    attachLog: true)
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Analyzing the code using SonarQube"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security scan using OWASP ZAP"
            }
            post{
                success {
                    emailext (to: "chanshut@gmail.com",
                    subject: "Security Scan Status",
                    body: "Security Scan Status was successful!",
                    attachLog: true)
                }
                failure {
                    emailext (to: "chanshut@gmail.com",
                    subject: "Security Scan Status",
                    body: "Security Scan was failed :(",
                    attachLog: ture)
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying the application to the staging server (AmazonEC2)"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the application to the production server (AmazonEC2)"
            }
        }
    }
}
