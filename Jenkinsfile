pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }

    post {
        success {
            slackSend(channel: 'C09AK2QM6M6', message: "✅ Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
        failure {
            slackSend(channel: 'C09AK2QM6M6', message: "❌ Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
    }
}