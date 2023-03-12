pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t msd967/web-app:latest .'
            }
        }
        stage('Push') {
            steps {
                withCredentials([string(credentialsId: 'msd967', variable: 'DOCKERHUB_CREDENTIALS')]) {
                    sh 'docker login -u msd967 -p $DOCKERHUB_CREDENTIALS'
                }
                sh 'docker push msd967/web-app:latest

