pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupération du code source depuis le référentiel Git
                checkout([$class: 'GitSCM', branches: [[name: '*/master']]])
            }
        }
        // Ajoutez d'autres étapes au besoin

     

    stage('Install Dependencies') {
        steps {
            script {
                // Installation de Node.js
                def nodejsInstallation = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
                nodejs(nodeJSInstallationName: nodejsInstallation, configId: null)

                // Installation des dépendances Angular
                sh 'npm install'
            }
        }
    }

    stage('Build') {
        steps {
            script {
                // Construction de l'application Angular
                sh 'ng build --prod'
            }
        }
    }
}


}
