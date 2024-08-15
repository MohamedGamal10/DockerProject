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

        stage('Push Docker Image') {
            steps {
                script {
                     withCredentials([usernamePassword(credentialsId: 'docker_hub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) 
                    {
                        sh '''
                        echo "$PASSWORD" | docker login -u "$USERNAME" --password-stdin
                        docker push "$USERNAME"/my-react-app:${env.BUILD_NUMBER}
                        '''   
                    }
                }
            }
        }
    }
  }

