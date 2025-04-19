pipeline {
    agent any

    stages {
        stage('Build Flask Image') {
            steps {
                dir('flask_app') {
                    bat 'docker build -t flask-app .'
                }
            }
        }
        stage('Build Django Image') {
            steps {
                dir('django_app') {
                    bat 'docker build -t django-app .'
                }
            }
        }
        stage('Compose Up') {
            steps {
                bat 'docker-compose up -d'
            }
        }
    }
}
