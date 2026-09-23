pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Show Build Info') {
            steps {
                echo "BUILD_NUMBER: ${env.BUILD_NUMBER}"
                echo "JOB_NAME: ${env.JOB_NAME}"
                echo "WORKSPACE: ${env.WORKSPACE}"
            }
        }
        
        stage('Run Linter') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'pip install flake8 --user || true'
                        sh 'python3 -m flake8 app.py || python -m flake8 app.py || true'
                    } else {
                        bat 'pip install flake8 || true'
                        bat 'python -m flake8 app.py || true'
                    }
                }
            }
        }
