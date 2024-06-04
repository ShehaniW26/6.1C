pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building the code using Maven123."

            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests with JUnit and integration tests with Selenium and Postman."
            }
		post {
                success {
                    emailext attachLog: true,
                    subject: "Tests Completed Successfully",
		    body: "Unit and Integration Tests are completed successfully.",
                    to: "shehani.wickremasekera@gmail.com"  
                }
                failure {
                    emailext attachLog: true,
                    subject: "Tests Failed",
		    body: "Unit and Integration Tests got failed. Check the logs for details.",
                    to: "shehani.wickremasekera@gmail.com" 
                }
            }
        }
    }
}
