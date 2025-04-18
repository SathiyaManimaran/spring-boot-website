pipeline {
    agent any

    triggers {
        // Optional: trigger by polling
        // pollSCM('H/5 * * * *') 
    }

    stages {
        stage('Build') {
            steps {
                echo "Building from develop branch"
            }
        }
    }
}
