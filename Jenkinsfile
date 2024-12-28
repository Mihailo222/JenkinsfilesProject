pipeline {
    agent { label 'NodeFromRemote' }

    stages {
        stage('Checkout Repository') { //generalno nista nece da radi bez checkout-a
            steps {
                echo "Stage: ${STAGE_NAME}"
                checkout scm
            }
        }

        stage('Print Workspace') {
            steps {
                echo "Stage: ${STAGE_NAME}"

                script {
                    echo "The current workspace is: ${env.WORKSPACE}"
                }
            }
        }

        stage('Listing a workspace of a current build on a current branch') {
            steps {
                echo "Stage: ${STAGE_NAME}"
                script {
                sh "ls -la \"${env.WORKSPACE}\""
                }
            }
        }

        stage('Delete Workspace') { //on ovde napravi workspaces.txt fajl u koji mi kaze e, ovo su ti svi buildovi koje si izvrsio
            steps {
                echo "Stage: ${STAGE_NAME}"
                    script {
                 cleanWs() //i nakon toga ti samo obrise taj ceo folder koji je WORKSPACE tog brancha
                    }
                echo "Listing files after cleanWs()."
                script {
                sh "ls -la /home/jenkins/workspace"
                }
                }
        }

      /*  stage('Odlazak u @tmp folder da se obrise'){
            echo "Stage: ${STAGE_NAME}"
            steps{
                step {
                    dir("${env.WORKSPACE}"){
                        deleteDir()
                    }

                }
                
            }
        }*/




















        
    }
}
