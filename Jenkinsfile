pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout du code depuis le référentiel Git
                git 'https://github.com/mayssa14/Docker-Pipeline.git'
            }
        }

        stage('Build') {
            steps {
                // Exemple avec Maven pour un projet Java, ajustez selon votre langage et outil de build
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Exemple de commandes pour exécuter des tests (ajustez en fonction de votre stack de test)
                sh 'npm install'
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Exemple de construction et de déploiement d'une image Docker (ajustez selon vos besoins)
                sh 'docker build -t mon-image:latest .'
                sh 'docker push mon-image:latest'
            }
        }
    }

    post {
        success {
            // Actions à prendre en cas de succès (notifications, déploiements supplémentaires, etc.)
        }
        failure {
            // Actions à prendre en cas d'échec (notifications, rollback, etc.)
        }
    }
}
