pipeline {
    agent any
    stages {
        stage('Checkout') {
            // Этап для получения исходного кода из репозитория
            steps {
                sh 'echo "Checkout..."'
                git(
                    url: "https://github.com/AlexAristov/jenkins.git",
                    branch: "main",
                    changelog: true,
                    poll: true
                )
            }
        }
        stage('Build') {
            steps {
                // Команды для сборки вашего проекта
                sh 'echo "Building..."'
                sh "mvn clean package"
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
                sh "cp ./target/jenkins-1.0-SNAPSHOT.war /opt/tomcat/webapps"
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