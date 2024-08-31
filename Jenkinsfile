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
                echo 'Executing: Running tests with Maven'
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
                echo 'Executing: Code quality analysis using Checkstyle'
                sh 'mvn checkstyle:check'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Code Quality Check Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Code Quality Check stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Security Scan Stage') {
            steps {
                echo 'Executing: Performing security scan with OWASP Dependency-Check'
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
                echo 'Executing: Deployment to staging - displaying deployment instructions'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Deploy to Staging Stage Notification: ${currentBuild.fullDisplayName}",
                         body: "The Deploy to Staging stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs."
                }
            }
        }
        stage('Integration Testing on Staging') {
            steps {
                echo 'Executing: Running integration tests on the staging environment'
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
                echo 'Executing: Deployment to production - displaying deployment instructions'
            }
            post {
                always {
                    mail to: 'ezenchinenye@gmail.com',
                         subject: "Deploy to Production Stage Notification: ${currentBuild.fullDisplayName}",
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
