pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo "Obteniendo el código desde GitHub"
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "No hay build real porque es HTML, pero simulamos el proceso"
                sh 'echo "Build completado correctamente"'
            }
        }

        stage('Test') {
            steps {
                echo "No hay pruebas automáticas, pero simulamos un test"
                sh 'echo "Test exitoso"'
            }
        }

        stage('Package') {
            steps {
                echo "Empaquetando el proyecto en release.zip"
                sh 'zip -r release.zip .'
            }
        }
    }

    post {
        success {
            echo "Pipeline finalizado con éxito."
            archiveArtifacts artifacts: 'release.zip', fingerprint: true
        }
    }
    failure {
        echo "Falló el release."
    }
}
