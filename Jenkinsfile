pipeline {
    agent any

    tools {
        nodejs "NodeJS 18"  // The NodeJS version you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Divyam0017/ci-cd-nodejs-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run App Test') {
            steps {
                // Start the app in background to verify it runs, then kill it
                sh 'nohup npm start & sleep 3 && pkill node'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t nodejs-demo-app .'
                }
            }
        }
    }
}
