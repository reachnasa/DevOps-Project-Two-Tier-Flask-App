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
                sh 'sudo docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                // existing container if they are running
                sh 'sudo docker compose down || true'
                // start app, rebuilding flask image
                sh 'sudo docker compose up -d --build'
            }
        }
    }
}