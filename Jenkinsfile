pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/MEGHAAMANICKAM/my-docker-app.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t meghaamanickam/meghaa-app .'
            }
        }

        stage('DockerHub Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'USER',
                    passwordVariable: 'PASS'
                )]) {
                    sh 'echo $PASS | docker login -u $USER --password-stdin'

                }
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push meghaamanickam/meghaa-app'
            }
        }
    }
}
