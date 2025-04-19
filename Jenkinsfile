pipeline {
    agent any

    stages {
        stage('Build Flask Image') {
            steps {
                dir('flask_app') {
                    script {
                        docker.build('flask-app')
                    }
                }
            }
        }
        stage('Build Django Image') {
            steps {
                dir('django_app') {
                    script {
                        docker.build('django-app')
                    }
                }
            }
        }
        stage('Compose Up') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
