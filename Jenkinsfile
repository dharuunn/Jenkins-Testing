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
                sh 'pip install flake8 --user || pip install flake8 || true'
                
                sh 'python3 -m flake8 app.py || python -m flake8 app.py || flake8 app.py'
            }
        }
    }
}
