pipeline{
    agent any
    stages{
        stage('Clone Repo'){
            steps{
                git branch: 'main', url: https://github.com/adanshul/Dev-Ops-Project-Two-Tier-Flask-App.git'
            }
        }
        stage('Build Image'){
            steps{
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with docker-compose'){
            steps{
                // if there are any existing containers running
                sh 'docker compose down || true'
                // start app, rebuilding flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}