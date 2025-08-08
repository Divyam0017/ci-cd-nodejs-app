pipeline {
    agent any
    
    tools {
        nodejs 'node18'   // Name of the NodeJS tool you set up in Jenkins
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo '📥 Checking out source code from GitHub...'
                git branch: 'main', url: 'https://github.com/Divyam0017/ci-cd-nodejs-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo '📦 Installing project dependencies...'
                sh 'npm install'
            }
        }

        stage('Run App (Test)') {
            steps {
                echo '🚀 Starting the application briefly to verify it works...'
                sh 'node index.js & sleep 5'
                sh 'pkill node' // stop the app after 5 seconds
            }
        }
    }
}
