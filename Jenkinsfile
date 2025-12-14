pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'   // optional but recommended
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
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
