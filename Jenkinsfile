pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/JuanSG0512/simple-python-app-ci.git'
            }
        }
        stage('Instalar Python') {
            steps {
                sh 'apt-get update'
                sh 'apt-get install -y python3 python3-venv'
            }
        }
        stage('Instalar dependencias') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Ejecutar pruebas') {
            steps {
                sh 'python3 -m unittest discover'
            }
        }
    }
}
