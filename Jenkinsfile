pipeline {
    agent any
    
    // Trigger the pipeline on GitHub push events
    triggers {
        githubPush()
    }
    
    // Define environment variables
    environment {
        // Define your authentication token here (if needed for any step)
        AUTH_TOKEN = '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'
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Stage 1: Build - Build the code using a build automation tool (e.g., Maven)"
                echo "Tool: Maven"
                // Example command to build the project
                // Uncomment and adjust the following line as necessary
                // sh 'mvn clean install'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Stage 2: Unit and Integration Tests - Run unit tests and integration tests"
                echo "Tools: JUnit for unit tests and Selenium for integration tests"
                // Example command to run tests
                // Uncomment and adjust the following line as necessary
                // sh 'mvn test'
            }
            post {
                success {
                    echo 'Unit and Integration Tests completed successfully, sending email...'
                    emailext(
                        body: 'Unit and Integration Tests stage completed successfully.',
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Unit and Integration Tests Stage Successful',
                        attachLog: true
                    )
                }
                failure {
                    echo 'Unit and Integration Tests failed, sending email...'
                    emailext(
                        body: 'Unit and Integration Tests stage failed.',
                        to: 'karunaratnedinusha@gmail.com',
                        subject: 'Unit and Integration Tests Stage Failed',
                        attachLog: true
                    )
                }
            }
        }
        
        // Add similar stages and post conditions for the other stages
        
    }
    
    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline completed successfully, sending email...'
            emailext(
                to: 'karunaratnedinusha@gmail.com',
                subject: 'Pipeline Successful',
                body: 'The Jenkins pipeline completed successfully.',
                attachLog: true
            )
        }
        failure {
            echo 'Pipeline failed, sending email...'
            emailext(
                to: 'karunaratnedinusha@gmail.com',
                subject: 'Pipeline Failed',
                body: 'The Jenkins pipeline failed.',
                attachLog: true
            )
        }
    }
}



