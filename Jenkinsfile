pipeline {
    agent any

    tools {
        maven 'Maven 3.9.9'
    }

    stages {
        stage('Build Stage') {
            steps {
                echo 'Task: Build - Using Maven to clean and package the project'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Build Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Build stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Test Stage') {
            steps {
                echo 'Task: Test - Using Maven to run tests'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Test Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Test stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Task: Code Analysis - Performing a code quality check'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Code Quality Check Notification: ${currentBuild.fullDisplayName}",
                         body: "The Code Quality Check stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Security Scan Stage') {
            steps {
                echo 'Task: Security Scan - Performing a security scan'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Security Scan Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Security Scan stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Deploy to Staging Environment') {
            steps {
                echo 'Task: Deploy to Staging - Displaying deployment instructions'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Deploy to Staging Notification: ${currentBuild.fullDisplayName}",
                         body: "The Deploy to Staging stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Integration Testing on Staging') {
            steps {
                echo 'Task: Integration Tests - Running integration tests on the staging environment'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Integration Tests Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Integration Tests stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Deploy to Production Environment') {
            steps {
                echo 'Task: Deploy to Production - Displaying production deployment instructions'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Deploy to Production Notification: ${currentBuild.fullDisplayName}",
                         body: "The Deploy to Production stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
    }

    post {
        always {
            mail to: 'ezenchinenye@gmail.com',
                 subject: "Pipeline Summary: ${currentBuild.fullDisplayName}",
                 body: "The entire pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
        }
    }
}
