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
            agent any
            steps{
                sh 'docker-compose build'
            }
        }
        
        stage('Docker push'){
            agent any
            steps{
                withCredentials([usernamePassword(credentialsId: DOCKER_CREDENTIALS_ID, usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]){
                    sh "docker login -u ${DOCKER_USER} -p ${DOCKER_PASS}"
                    sh 'docker push mujtabaazizkhan/forlorn-pipeline-implementation:latest'
                }
            }
        }
    }
}
