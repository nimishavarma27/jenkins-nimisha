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
                echo "Checking index.html..."
                sh "test -f index.html"
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'index.html', fingerprint: true
            }
        }
    }

    post {
        success {
            echo "CI Pipeline Completed Successfully!"
        }
        failure {
            echo "Pipeline Failed!"
        }
    }
}