pipeline {
    agent any

    environment {
        // Define environment variables if needed (e.g., for Java or Maven)
        MAVEN_HOME = '/usr/local/maven'  // Update if necessary
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'  // Update to match your Java version
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the repository
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                script {
                    // Ensure Maven is installed on the Jenkins agent
                    echo "Building the project..."
                    sh 'mvn clean install -DskipTests'  // Use Maven to build the project
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    echo "Running tests..."
                    // Run tests with Maven (this will automatically find the tests in the `src/test/java` folder)
                    sh 'mvn test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying the application..."
                    // Add your deployment steps here (e.g., deploying to a server or cloud service)
                    // Example: sh 'scp target/*.jar user@server:/path/to/deploy'
                }
            }
        }
    }

    post {
        always {
            echo "Cleaning up after the build..."
            // Clean up any resources, such as temporary files or directories
        }
        
        success {
            echo "Build and tests completed successfully!"
        }
        
        failure {
            echo "Build failed. Please check the logs."
        }
    }
}

