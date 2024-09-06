pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9'
    }
    stages {
        stage('Build Stage') {
            steps {
                echo 'Task: Build - Using Maven to clean and package the project'
                bat 'echo mvn clean package > build_stage.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Build Stage Notification: ${currentBuild.fullDisplayName}",
                            body: "The Build stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'build_stage.log'
                }
            }
        }
        stage('Test Stage') {
            steps {
                echo 'Task: Test - Using Maven to run tests'
                bat 'echo mvn test > test_stage.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Test Stage Notification: ${currentBuild.fullDisplayName}",
                            body: "The Test stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'test_stage.log'
                }
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Task: Code Analysis - Print code quality analysis steps'
                bat 'echo Performing code analysis > code_quality_check.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Code Quality Check Notification: ${currentBuild.fullDisplayName}",
                            body: "The Code Quality Check stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'code_quality_check.log'
                }
            }
        }
        stage('Security Scan Stage') {
            steps {
                echo 'Task: Security Scan - Print security scan steps'
                bat 'echo Performing security scan > security_scan_stage.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Security Scan Stage Notification: ${currentBuild.fullDisplayName}",
                            body: "The Security Scan stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'security_scan_stage.log'
                }
            }
        }
        stage('Deploy to Staging Environment') {
            steps {
                echo 'Task: Deploy to Staging - Print deployment steps to staging'
                bat 'echo Deploying to staging > deploy_staging_environment.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Deploy to Staging Notification: ${currentBuild.fullDisplayName}",
                            body: "The Deploy to Staging stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'deploy_staging_environment.log'
                }
            }
        }
        stage('Integration Testing on Staging') {
            steps {
                echo 'Task: Integration Tests - Print integration tests steps on staging'
                bat 'echo Running integration tests on staging > integration_testing_staging.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Integration Tests Stage Notification: ${currentBuild.fullDisplayName}",
                            body: "The Integration Tests stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'integration_testing_staging.log'
                }
            }
        }
        stage('Deploy to Production Environment') {
            steps {
                echo 'Task: Deploy to Production - Print production deployment steps'
                bat 'echo Deploying to production > deploy_production_environment.log' // Simulating log generation
            }
            post {
                always {
                    emailext to: 'ezenchinenye@gmail.com',
                            subject: "Deploy to Production Notification: ${currentBuild.fullDisplayName}",
                            body: "The Deploy to Production stage of the pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                            attachLog: true,
                            attachmentsPattern: 'deploy_production_environment.log'
                }
            }
        }
    }
    post {
        always {
            emailext to: 'ezenchinenye@gmail.com',
                    subject: "Pipeline Summary: ${currentBuild.fullDisplayName}",
                    body: "The entire pipeline has completed with status: ${currentBuild.currentResult}. Please check the logs.",
                    attachLog: true,
                    attachmentsPattern: '**/*.log' // Attaches all log files generated throughout the pipeline
        }
    }
}
