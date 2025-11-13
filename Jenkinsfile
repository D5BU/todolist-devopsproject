pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/D5BU/todolist-devopsproject.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                powershell 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                powershell 'docker build -t todo-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                powershell 'docker run -d -p 3000:3000 todo-app'
            }
        }
    }
}
