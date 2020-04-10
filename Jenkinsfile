pipeline {
    agent { docker { image 'python:3.6.6' } }
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'echo hi'
            }
        }
    }
}