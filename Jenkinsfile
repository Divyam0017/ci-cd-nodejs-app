pipeline {
    agent any

    tools {
        nodejs "node18" // The NodeJS version you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Divyam0017/ci-cd-nodejs-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }

    }
}
