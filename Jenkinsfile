pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/prateek8731/sample-flask-app'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t flask-app .'
            }
        }
        stage('Test') {
            steps {
                sh 'pytest tests/'  // Optional: You should add test cases in a tests/ folder
            }
        }
        stage('Security Scan') {
            steps {
                sh 'dependency-check --scan ./ --out report'
            }
        }
    }
}
