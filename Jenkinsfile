pipeline {
    agent any

    stages {
        stage('Pull Repo') {
            steps {
              git url: 'https://github.com/MohamedGamal10/DockerProject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                  sh "docker build -t my-react-app:${env.BUILD_NUMBER} ."
                }
            }
        }
    }
  }

