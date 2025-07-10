pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/yourusername/flask-cicd-demo.git'
            }
        }
        stage('Build Image') {
            steps {
                script {
                    docker.build('flask-demo')
                }
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f flask-container || true'
                sh 'docker run -d -p 5000:5000 --name flask-container flask-demo'
            }
        }
    }
}
