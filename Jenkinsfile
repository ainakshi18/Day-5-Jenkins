pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add your build commands here
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment commands here
            }
        }
    }
    post {
    success {
        emailext(
            subject: "Build Succeeded: ${currentBuild.fullDisplayName}",
            body: "The build was successful.",
            to: 'horeainakshi97@gmail.com'
        )
    }
    failure {
        emailext(
            subject: "Build Failed: ${currentBuild.fullDisplayName}",
            body: "The build failed. Check the logs for more information.",
            to: 'horeainakshi97@gmail.com'
        )
    }
}

}
