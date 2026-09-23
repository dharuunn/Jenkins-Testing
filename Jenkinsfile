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
                echo "Simulating Linter check... Found unused import 'import os'!"
                error("Linting failed due to unused import statements.")
            }
        }
    }
}
