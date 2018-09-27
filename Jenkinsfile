pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'cd backend'
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}