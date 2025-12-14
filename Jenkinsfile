pipeline {
    agent any   // runs on Windows agent

    stages {

        stage('Clone Project') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/PraveenKuberABC/Amazon-Ecom.git'
            }
        }

        stage('Clean') {
            steps {
                bat 'mvn clean'
            }
        }

        stage('Compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully on Windows agent'
        }
        failure {
            echo '❌ Build failed on Windows agent'
        }
    }
}
