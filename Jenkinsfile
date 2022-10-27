pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }
    stages {
/*
        stage('Checkout') {
            git branch: 'main',
                url: 'https://github.com/mhca3465/do400-pipelines-control'
        }
*/
        stage('Backend Tests') {
            steps {
                sh 'node ./backend/test.js'
            }
        }
        stage('Frontend Tests') {
            steps {
                sh 'node ./frontend/test.js'
            }
        }
    }
}

// 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