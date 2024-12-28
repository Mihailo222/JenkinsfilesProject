pipeline {
    agent { label 'NodeFromRemote' }

    stages {
        stage('Checkout Repository') { //generalno nista nece da radi bez checkout-a
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

        stage('Delete Workspace') { //on ovde napravi workspaces.txt fajl u koji mi kaze e, ovo su ti svi buildovi koje si izvrsio
            steps {
                cleanWs() //i nakon toga ti samo obrise taj ceo folder koji je WORKSPACE tog brancha
            }
        }
    }
}
