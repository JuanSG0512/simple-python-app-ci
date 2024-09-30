pipeline {
    agent {
        docker { image 'python:3.9' }
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/JuanSG0512/simple-python-app-ci.git'
            }
        }
        stage('Instalar dependencias') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Ejecutar pruebas') {
            steps {
                sh 'python -m unittest discover'
            }
        }
    }
}
