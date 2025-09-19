pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build - Building with Maven'
                echo 'Tool: Maven (mvn clean package)'
                echo 'Task: Compile and package the application'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Tools: JUnit, TestNG, Jest'
                echo 'Task: Run unit tests and integration tests'
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Tool: SonarQube'
                echo 'Task: Analyze code quality and standards compliance'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Tool: OWASP Dependency Check'
                echo 'Task: Scan for security vulnerabilities'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Tool: AWS CLI, Docker'
                echo 'Task: Deploy application to staging environment'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Tools: Selenium, Postman/Newman'
                echo 'Task: Run tests in production-like environment'
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Tool: AWS CLI, Kubernetes'
                echo 'Task: Deploy application to production environment'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline completed - all 7 stages executed'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
