pipeline {
    agent any
    
    tools {
        nodejs "nodejs"
    }

    stages {
        stage('Install Packages') {
            steps {
                script {
                    sh 'yarn install'
                }
            }
        }

        stage('Install PM2') {
            steps {
                script {
                    sh 'npm install -g pm2'
                }
            }
        }

        stage('Run the App') {
            steps {
                script {
                    sh 'yarn start:pm2'
                    sleep 5
                }
            }
        }

        stage('Test the app') {
            steps {
                script {
                    sh 'curl http://localhost:3000/health'
                }
            }
        }
    }
}
