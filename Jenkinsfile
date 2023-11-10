pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                script {
                    docker.build("mon_application")
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    docker.image("angular20").run()
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    // Déployez votre application ici
                    // Vous pouvez utiliser docker-compose, kubectl, etc.
                }
            }
        }
    }
}
