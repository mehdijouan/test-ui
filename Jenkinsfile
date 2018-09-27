pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage('build') {
            steps {
                dir('backend') {
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }
    }
}