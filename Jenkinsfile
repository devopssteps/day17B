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
            slackSend(channel: 'https://app.slack.com/client/T099LRSA42F/C09AK2QM6M6?entry_point=no_workspace', message: "✅ Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
        failure {
            slackSend(channel: 'https://app.slack.com/client/T099LRSA42F/C09AK2QM6M6?entry_point=no_workspace', message: "❌ Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}")
        }
    }
}