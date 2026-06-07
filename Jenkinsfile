pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Docker Build') {
            steps {
                bat 'docker build -t java-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker run java-app'
            }
        }
    }
}