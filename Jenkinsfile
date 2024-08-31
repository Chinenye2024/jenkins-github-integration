  pipeline {
    agent any

    tools {
        maven 'Maven 3.9.9'
    }

    stages {
        stage('Build Stage') {
            steps {
                echo 'Executing: Build process with Maven - cleaning and packaging the project'
            }
        }
        stage('Test Stage') {
            steps {
                echo 'Executing: Running tests with Maven'
            }
            post {
                success {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Pipeline Success Notification: ${currentBuild.fullDisplayName}",
                         body: "The Test stage completed successfully."
                }
                failure {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Pipeline Failure Notification: ${currentBuild.fullDisplayName}",
                         body: "The Test stage encountered a failure. Please review the logs."
                }
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Executing: Code quality analysis using Checkstyle'
                sh 'mvn checkstyle:check'
            }
        }
        stage('Security Scan Stage') {
            steps {
                echo 'Executing: Performing security scan with OWASP Dependency-Check'
            }
            post {
                success {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Pipeline Success Notification: ${currentBuild.fullDisplayName}",
                         body: "The Security Scan stage completed successfully."
                }
                failure {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Pipeline Failure Notification: ${currentBuild.fullDisplayName}",
                         body: "The Security Scan stage encountered a failure. Please review the logs."
                }
            }
        }
        stage('Deploy to Staging Environment') {
            steps {
                echo 'Executing: Deployment to staging - displaying deployment instructions'
            }
        }
        stage('Integration Testing on Staging') {
            steps {
                echo 'Executing: Running integration tests on the staging environment'
            }
        }
        stage('Deploy to Production Environment') {
            steps {
                echo 'Executing: Deployment to production - displaying deployment instructions'
            }
        }
    }

    post {
        always {
            mail to: 'ezenchinenye@gmail.com',
                 subject: "Pipeline Summary: ${currentBuild.fullDisplayName}",
                 body: "The pipeline completed with the status: ${currentBuild.currentResult}. Please check the logs."
        }
    }
}
