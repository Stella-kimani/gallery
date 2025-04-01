
pipeline {
    agent any

    environment {
        DEPLOY_ENV = 'render'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }

        stage('Deploy to Render') {
            steps {
                script {
                    sh 'node server'
                }
            }
        }
    }

    post {
        success {
            slackSend (channel: '#Stella-slack-channel', message: "Build successful: ${BUILD_ID}. View it here: https://your-render-site-link")
        }
        failure {
            slackSend (channel: '#Stella-slack-channel', message: "Build failed: ${BUILD_ID}.")
        }
    }
}
