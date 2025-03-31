pipeline {
  agent any
  stages {
    stage('Install Dependencies') {
      steps {
        script {
          // Install dependencies using npm
          sh 'npm install'
        }
      }
    }
    stage('Deploy to Render') {
      steps {
        script {
          // Deploy the app using Render's deployment command
          sh 'npm start'
        }
      }
    }
  }
}
