pipeline {
    agent { label 'agent1' }

    stages {
        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }

        stage('Print Workspace') {
            steps {
                script {
                    echo "The current workspace is: ${env.WORKSPACE}"
                }
            }
        }
    }
}
