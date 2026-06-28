pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out successfully'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t flaskmongo:v2 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f flaskapp || true'
                sh 'docker run -d --name flaskapp -p 5000:5000 flaskmongo:v2'
            }
        }
    }
}
