pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    environment {
        EMAIL_RECIPIENT = 'teddyhiny@gmail.com'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build – Install dependencies and prepare Node.js application.'
                echo 'Tool: npm (Node Package Manager)'
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Build Stage: ${currentBuild.result}",
                        body: "The 'Build' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Stage 2: Unit and Integration Tests – Run unit and integration tests.'
                    echo 'Tools: Jest'
                    sh 'echo "Running Jest tests..."'
                }
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Unit and Integration Tests: ${currentBuild.result}",
                        body: "The 'Unit and Integration Tests' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis – Perform static code analysis for quality and standards.'
                echo 'Tool: ESLint'
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Code Analysis: ${currentBuild.result}",
                        body: "The 'Code Analysis' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Security Scan') {
            steps {
                script {
                    echo 'Stage 4: Security Scan – Scan for known vulnerabilities in dependencies.'
                    echo 'Tool: npm audit'
                    sh 'echo "Running npm audit..."'
                }
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Security Scan: ${currentBuild.result}",
                        body: "The 'Security Scan' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging – Deploy the Node.js app to a staging server on AWS EC2.'
                echo 'Tool: Ansible'
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Deploy to Staging: ${currentBuild.result}",
                        body: "The 'Deploy to Staging' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging – Run integration tests in staging environment.'
                echo 'Tools: Jest'
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Integration Tests on Staging: ${currentBuild.result}",
                        body: "The 'Integration Tests on Staging' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production – Deploy the application to the production server on AWS EC2.'
                echo 'Tool: Ansible'
            }
            post {
                always {
                    emailext(
                        subject: "Jenkins Job - Deploy to Production: ${currentBuild.result}",
                        body: "The 'Deploy to Production' stage has completed with status: ${currentBuild.result}",
                        to: "${EMAIL_RECIPIENT}",
                        attachLog: true
                    )
                }
            }
        }
    }
}
