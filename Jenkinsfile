pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo "Build the code using a build automation tool (e.g., Maven) to compile and package your code."
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests to ensure the code functions as expected."
                echo "Tools: JUnit for unit tests and Selenium for integration tests."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Integrate a code analysis tool (e.g., SonarQube) to analyze the code and ensure it meets industry standards."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Perform a security scan on the code using a tool (e.g., OWASP ZAP) to identify any vulnerabilities."
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to a staging server (e.g., AWS EC2 instance)."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the application to a production server (e.g., AWS EC2 instance)."
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline finished successfully.'
            sendNotificationEmail("Success")
        }
        failure {
            echo 'Pipeline failed.'
            sendNotificationEmail("Failure")
        }
    }
}

def sendNotificationEmail(status) {
    emailext(
        to: 'your_email@example.com',
        subject: "Pipeline ${status}",
        body: "Pipeline ${status}.",
        attachLog: true
    )
}
