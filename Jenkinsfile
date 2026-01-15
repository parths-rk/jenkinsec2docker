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
        stage('Run Docker Container'){
            steps{
                sh '''
                docker stop jenkinsec2docker || true
                docker rm jenkinsec2docker || true
                docker run -d -p 3000:3000 \
                --name jenkinsec2docker \
                parths-rk/jenkinsec2docker:latest '''
            }
        }

        stage('Push Docker Image'){
            steps{
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhubCreds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
             ]))
             {
                sh '''
                echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                docker push parths-rk/jenkinsec2docker:latest
                '''
             }
            }
        }
    }
}