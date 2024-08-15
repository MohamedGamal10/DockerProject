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
                  sh " echo ${env.BUILD_NUMBER}"
                }
            }
        }
    }
  }

