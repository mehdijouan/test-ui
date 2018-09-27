pipeline {
    agent {
        docker { image 'node:alpine' }
    }
    stages {
        stage('build') {
            dir 'backend'
                steps {
                    sh 'npm install'
                    sh 'npm run build'
            }
        }
    }
}