pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage('build backend') {
            steps {
                dir('backend') {
                    sh 'docker build -t testbackend -f Dockerfile.production .'
                    sh 'npm run build'
                }
            }
        }
        stage('Build Docker test'){
            steps {
                dir('backend') {
                    sh 'docker build -t backend-test -f Dockerfile.test --no-cache .'
                    sh 'docker run --rm backend-test'
                    sh 'docker rmi backend-test'
                }
            }
        }
    }
}