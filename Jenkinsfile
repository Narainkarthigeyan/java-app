pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<username>/java_app.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t java-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker rm -f java-demo-container || exit 0'
                bat 'docker run --name java-demo-container java-app'
            }
        }
    }
}