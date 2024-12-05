pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/MaxymZapotockiy27/MyPipelineApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/bin/**/*', fingerprint: true
        }
    }
}
