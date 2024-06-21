pipeline {
    agent any
    stages {
        stage('Checkout') {
            // Этап для получения исходного кода из репозитория
            steps {
                sh 'echo "Checkout..."'
                checkout scm // Команда для получения исходного кода из репозитория, указанного в настройках Jenkins
            }
        }
        stage('Build') {
            steps {
                // Команды для сборки вашего проекта
                sh 'echo "Building..."'
                sh "hostname"
            }
        }
        stage('Test') {
            steps {
                // Команды для тестирования вашего проекта
                sh 'echo "Testing..."'
            }
        }
        stage('Deploy') {
            steps {
                // Команды для развертывания вашего проекта
                sh 'echo "Deploying..."'
            }
        }
    }
    post {
        success {
            // Действия после успешного выполнения pipeline
            sh 'echo "Success!"'
        }
        failure {
            // Действия в случае ошибки
            sh 'echo "Failed!"'
        }
    }
}