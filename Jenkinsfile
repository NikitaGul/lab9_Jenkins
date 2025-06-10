pipeline {
    agent any

    environment {
        NODE_ENV = 'production'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/NikitaGul/lab9_Jenkins.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    ssh -i /var/lib/jenkins/.ssh/id_rsa user@your-server-ip '
                    cd /path/to/project &&
                    git pull &&
                    npm install &&
                    npm run build &&
                    pm2 restart all'
                '''
            }
        }
    }
}
