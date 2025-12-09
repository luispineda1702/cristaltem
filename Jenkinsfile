pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Descargando el código del repositorio..."
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Compilando proyecto HTML..."'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Ejecutando pruebas simuladas..."'
            }
        }

        stage('Package Release') {
            steps {
                sh 'echo "Generando release..."'
                sh 'zip -r release.zip .'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'release.zip', fingerprint: true
            echo "Release generado exitosamente."
        }
        failure {
            echo "Falló el pipeline."
        }
    }
}
