pipeline {
    agent any

    tools {
        nodejs 'NodeJS_18'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/NikitaGul/lab9_Jenkins.git'
            }
        }

        stage('Install dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Run Locally') {
            steps {
                bat 'npm start'
            }
        }
    }
}
