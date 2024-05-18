pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Build') {
            steps {
                echo "Build the code using a build automation tool"
                echo "Tool: Maven"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests to ensure the code functions as expected"
                echo "Tools: JUnit for unit tests and Selenium for integration tests"
            }
            post {
                success {
                    emailext(
                        body: 'Test stage completed successfully.',
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Test Stage Successful',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        body: 'Test stage failed.',
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Test Stage Failed',
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Integrate a code analysis tool to analyze the code and ensure it meets industry standards"
                echo "Tools: Jenkins with SonarQube and Checkmarx"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Perform a security scan on the code using a tool to identify any vulnerabilities"
                echo "Tools: OWASP ZAP (Zed Attack Proxy)"
            }
            post {
                success {
                    emailext(
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Security Scan Successful',
                        body: 'Security scan completed successfully.',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Security Scan Failed',
                        body: 'Security scan failed.',
                        attachLog: true
                    )
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment to ensure the application functions as expected."
                echo "Tools: Selenium WebDriver"
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploy the application to a production server"
                echo "Tools: AWS Elastic Beanstalk"
            }
        }
    }
}
