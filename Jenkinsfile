pipeline {
    agent any
    parameters {
        choice(
            name: 'ENVIRONMENT', 
            choices: ['dev', 'staging', 'prod'], 
            description: 'Select the target environment for execution'
        )
        booleanParam(
            name: 'RUN_EXTRA_CHECK', 
            defaultValue: false, 
            description: 'Check this box to run the Extra Check validation stage'
        )
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Show Parameter') {
            steps {
                echo "Selected Target Environment: ${params.ENVIRONMENT}"
            }
        }
        stage('Extra Check') {
            when {
                expression { params.RUN_EXTRA_CHECK == true }
            }
            steps {
                echo "Executing extensive environment health checks..."
            }
        }
    }
}
