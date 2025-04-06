pipeline {
    agent any
    environment {
        GIT_CREDENTIALS = 'SathiyaManimaran'  // The ID of the credentials you created
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    // Use the Git credentials to clone the repository
                    git(
                        url: 'https://github.com/SathiyaManimaran/spring-boot-website.git',
                        credentialsId: "${env.GIT_CREDENTIALS}"
                    )
                }
            }
        }
        stage('Build') {
            steps {
                echo "Building your project..."
                // Add build steps here
            }
        }
    }
}
