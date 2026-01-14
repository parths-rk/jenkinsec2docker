pipeline {
    agent any

    stages{
        stage('Check Node Version'){
            steps{
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Install Dependencies'){

            steps{
                dir('app'){
                    sh 'npm install'
                }
            }
        }
        stage('Run Tests'){
            steps{
                dir('app'){
                    sh 'npm test'
                }
            }
        }
        stage('Build Docker Image'){
            steps{
                sh 'docker build -t parths-rk/jenkinsec2docker:latest .'
            }
        }
    }
}