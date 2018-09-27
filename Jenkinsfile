pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage('Test') {
            dir('backend') {
                steps {
                    sh 'cd backend'
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
    }
}