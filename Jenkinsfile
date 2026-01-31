pipeline {
    agent any

    triggers {
        githubPush()
    }

    environment {
        IMAGE_NAME = "meghaamanickam/meghaa-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/MEGHAAMANICKAM/my-docker-app.git'
            }
        }

        stage('Build Image') {
            steps {
                sh "docker build -t $IMAGE_NAME:$IMAGE_TAG ."
            }
        }

        stage('DockerHub Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds1',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh "echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin"
                }
            }
        }

        stage('Push Image') {
            steps {
                sh "docker push $IMAGE_NAME:$IMAGE_TAG"
            }
        }
    }
}

