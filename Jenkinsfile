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

                /*script {
                    sh "ls -la \"${env.WORKSPACE}\""
                }*/
//**********************************************************************************************
                script {
                 cleanWs() //i nakon toga ti samo obrise taj ceo folder koji je WORKSPACE tog brancha
                    }
                echo "Listing files after cleanWs()."
                script {
                sh "ls -la \"${env.WORKSPACE}\"" //sve iz doticnog foldera je obrisano
                }
//**********************************************************************************************                
                dir("${env.WORKSPACE}@tmp"){
                        deleteDir() //brise sve sto se nalazi u datom dir-u, ali ne i dir
                }
                    
                echo "Listing files after deleting ${env.WORKSPACE}@tmp"
                    script {
                        sh "ls -la ${env.WORKSPACE}@tmp"
                    }
//**********************************************************************************************
                dir("${env.WORKSPACE}"){
                        deleteDir() //brise sve sto se nalazi u datom dir-u, ali ne i dir
                }
                    
                echo "Listing files after deleting ${env.WORKSPACE}"
                    script {
                        sh "ls -la ${env.WORKSPACE}"
                    }
                
            }
        }
    }                
}
