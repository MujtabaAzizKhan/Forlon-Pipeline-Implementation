pipeline {
    agent any
    
    environment {
        DOCKER_CREDENTIALS_ID = 'f6009f42-fc72-4c16-b3bc-bd7551613a70'
        DOCKER_REGISTRY = 'Docker Hub'
        TAG = "${env.BUILD_NUMBER}"
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

        stage ('Docker tag'){
            steps{
                sh 'docker tag mujtabaazizkhan/forlorn-pipeline-implementation:latest mujtabaazizkhan/forlorn-pipeline-implementation:v${TAG}'
            }
        }
        
        stage('Docker push') {
            steps {
                script {
                    docker.withRegistry('', DOCKER_CREDENTIALS_ID) {
                        sh 'docker push mujtabaazizkhan/forlorn-pipeline-implementation:v${TAG}'
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
