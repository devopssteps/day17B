pipeline {
    agent any
    environment {
        IMAGE_NAME = "devopssteps/my-docker-app-17b"
        IMAGE_TAG = "latest"
    }


    stages {
        
        stage('Build Docker Image') {
            steps {
                script {
                    //dockerImage = docker.build("myapp:${env.BUILD_NUMBER}")
                    sh "docker build -t ${IMAGE_NAME}:${IMAGE_TAG} ."    
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    //dockerImage.run("-p 5000:5000")
                     sh "docker run -d -p 5000:5000 --name demo-container ${IMAGE_NAME}:${IMAGE_TAG}" 
                }
            }
        }
    }
}
