pipeline{
    agent any
    stages{
        stage('Clone repo'){
            steps{
                git branch: 'main', url: 'https://github.com/reachnasa/DevOps-Project-Two-Tier-Flask-App.git'
            }
        }
        stage('Build image'){
            steps{
                sh '/usr/local/bin/docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                // existing container if they are running
                sh '/usr/local/bin/docker compose down || true'
                // start app, rebuilding flask image
                sh '/usr/local/bin/docker compose up -d --build'
            }
        }
    }
}