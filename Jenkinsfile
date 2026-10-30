pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'docker run --rm python:3.15.2-alpine3.24 python --version'
            }
        }
    }
}
