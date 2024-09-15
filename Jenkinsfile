pipeline {
    agent any
    
    environment {
        DOCKER_CREDENTIALS_ID = 'f6009f42-fc72-4c16-b3bc-bd7551613a70'
        DOCKER_REGISTRY = 'Docker Hub'
    }

    stages {
        
        stage('Github Connection'){
            steps{
                git branch: 'main', url: 'https://github.com/MujtabaAzizKhan/Forlorn-Pipeline-Implementation'
            }
        }
        
        stage('Docker-compose build'){
            steps{
                sh 'docker-compose build'
            }
        }
        
        // stage('Docker push'){
        //     steps{
        //         withCredentials([usernamePassword(credentialsId: DOCKER_CREDENTIALS_ID, usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]){
        //             sh """
        //                 echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
        //                 docker push mujtabaazizkhan/forlorn-pipeline-implementation:latest
        //                 docker logout
        //             """
        //         }
        //     }
        // }
        stage('Docker push') {
            steps {
                script {
                    docker.withRegistry('', DOCKER_CREDENTIALS_ID) {
                        sh 'docker push mujtabaazizkhan/forlorn-pipeline-implementation:latest'
                    }
                }
            }
        }
    }
    
    post {
        always {
            sh 'docker logout'
        }
    }
}
