pipeline {
    agent any

    environment {
        // Kalau perlu, bisa tambahkan credential GitHub
        // GITHUB_CREDENTIALS = 'github-token'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout branch main
                git branch: 'main', url: 'https://github.com/Yano378-git/jenkins-pipeline-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                // Tambahkan perintah build sesuai projectmu, misal:
                // sh './build.sh'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Tambahkan perintah test jika ada, misal:
                // sh 'npm test' atau 'pytest'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project..."
                // Tambahkan perintah deploy jika diperlukan
            }
        }
    }

    post {
        success {
            echo "Pipeline finished successfully!"
        }
        failure {
            echo "Pipeline failed. Check logs for details."
        }
    }
}
