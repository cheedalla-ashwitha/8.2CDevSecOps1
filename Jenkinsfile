pipeline {
    agent any

    // Auto-trigger on a schedule (no webhook required)
    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Tool: Maven'
                echo 'Task: Compile and package the application (mvn clean package)'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Tool: JUnit'
                echo 'Task: Execute unit tests and basic integration tests'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Tool: SonarQube (local instance)'
                echo 'Task: Analyze code quality, maintainability, and coding standards'
            }
        }

        stage('SonarCloud Analysis') {
            steps {
                echo 'Stage 3b: SonarCloud Analysis'
                echo 'Tool: SonarCloud with Jenkins credentials (SONAR_TOKEN)'
                echo 'Task: Upload code analysis results and coverage reports to SonarCloud dashboard'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Tool: OWASP Dependency-Check'
                echo 'Task: Scan project dependencies for known vulnerabilities (CVEs)'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Tool: AWS CLI'
                echo 'Task: Deploy the application artifact to a staging environment (e.g., EC2)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Tool: Selenium'
                echo 'Task: Run end-to-end tests against the staging environment'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Tool: Kubernetes (kubectl)'
                echo 'Task: Roll out the new version to the production cluster'
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed - all 8 stages executed'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
