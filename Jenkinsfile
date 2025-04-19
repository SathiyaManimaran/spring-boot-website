pipeline {
    agent { label 'slave3' }

  triggers {
        pollSCM('H/5 * * * *') // Check for changes every 5 minutes
    }
    stages {
        stage('Build') {
            steps {
                echo "Building from develop branch"
            }
        }
    }
}
