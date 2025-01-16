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
        always {
            emailext(
                subject: "Jenkins Build Notification: ${currentBuild.fullDisplayName}",
                body: """\
                    Build Status: ${currentBuild.currentResult}
                    Project: ${env.JOB_NAME}
                    Build Number: ${env.BUILD_NUMBER}
                    Build URL: ${env.BUILD_URL}
                """,
                to: 'horeainakshi97@gmail.com',
                from:'horeainakshi97@gmail.com',
                replyTo:'horeainakshi97@gmail.com',
                mimeType: 'text/html'
            )
        }
    }

}
