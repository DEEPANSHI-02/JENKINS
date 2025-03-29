pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: 'github-token', url: 'https://github.com/DEEPANSHI-02/JENKINS.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Deployment logic goes here
            }
        }
    }

    post {
        success {
            echo '🎉 Build & Deployment Successful!'
        }
        failure {
            echo '❌ Build Failed!'
        }
    }
}
