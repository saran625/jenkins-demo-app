pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/saran625/jenkins-demo-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("jenkins-demo-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    dockerImage.run('-d -p 5000:5000')
                }
            }
        }
    }
}
