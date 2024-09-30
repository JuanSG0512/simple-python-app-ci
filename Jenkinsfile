pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/JuanSG0512/simple-python-app-ci.git'
            }
        }

        stage('Install Python') {
            steps {
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y python3 python3-venv'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt || true'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && python -m unittest discover -s .'
            }
        }
    }
}
