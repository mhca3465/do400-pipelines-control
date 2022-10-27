pipeline {
    agent {
        node {
            label 'nodejs'
        }
    }
    parameters {
        booleanParam(name: "RUN_FRONTEND_TESTS", defaultValue: true)
    }
    stages {
        stage('Run Tests') {
            parallel {
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
                    when { expression { params.RUN_FRONTEND_TESTS } }
                    steps {
                        sh 'node ./frontend/test.js'
                    }
                }
            }
        }
    }
}

// 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