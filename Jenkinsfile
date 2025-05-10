pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build – Install dependencies and prepare Node.js application.'
                echo 'Tool: npm (Node Package Manager)'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests – Run unit and integration tests.'
                echo 'Tools: Jest'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis – Perform static code analysis for quality and standards.'
                echo 'Tool: ESLint'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan – Scan for known vulnerabilities in dependencies.'
                echo 'Tool: npm audit'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging – Deploy the Node.js app to a staging server on AWS EC2.'
                echo 'Tool: Ansible'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging – Run integration tests in staging environment.'
                echo 'Tools: Jest'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production – Deploy the application to the production server on AWS EC2.'
                echo 'Tool: Ansible'
            }
        }
    }
}
