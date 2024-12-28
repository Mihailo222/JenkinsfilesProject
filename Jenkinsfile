pipeline {
    agent { label 'NodeFromRemote' }

    stages {
        stage('Print Workspace') {
            steps {
                script {
                    echo "The current workspace is: ${env.WORKSPACE}"
                }
            }
        }
    }
}

