pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code from GitHub..."
                git branch: 'main', url: 'https://github.com/Yano378-git/jenkins-pipeline-demo.git', credentialsId: 'github-token'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                // Tambahkan perintah build jika ada
                // sh 'npm install'
                // sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Tambahkan perintah test jika ada
                // sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying project to Jenkins workspace..."
                // Workspace Jenkins menjadi tempat “deploy” web
                sh 'mkdir -p $WORKSPACE/deploy'
                sh 'cp -r * $WORKSPACE/deploy/'
            }
        }

        stage('Publish Web') {
            steps {
                echo "Publishing web via HTML Publisher..."
                publishHTML([allowMissing: false,
                             alwaysLinkToLastBuild: true,
                             keepAll: true,
                             reportDir: 'deploy',
                             reportFiles: 'index.html',
                             reportName: 'Front-end Web'])
            }
        }
    }

    post {
        success {
            echo "Pipeline finished successfully! Open 'Front-end Web' in Jenkins UI to see the web."
        }
        failure {
            echo "Pipeline failed. Check console output for details."
        }
    }
}
