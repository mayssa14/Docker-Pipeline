pipeline {
    agent any

    environment {
        // Set environment variables
        DOCKER_HUB_CREDENTIALS = credentials('5e95b6e4-56b6-4f0b-8142-ac7adc984dbc')
        DOCKER_IMAGE_NAME = 'maayssaa/hello-world'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your SCM
                git 'https://github.com/mayssa14/Docker-Pipeline.git'
            }
        }

        stage('Build and Push Docker Image') {
            steps {
                // Build Docker image
                script {
                    docker.withRegistry('https://registry.hub.docker.com', '5e95b6e4-56b6-4f0b-8142-ac7adc984dbc') {
                        def customImage = docker.build(DOCKER_IMAGE_NAME)
                        customImage.push()
                    }
                }
            }
        }
    }
}
