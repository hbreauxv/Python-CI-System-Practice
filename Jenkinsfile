pipeline {
    agent { docker { image 'python:3.6.6' } }
    stages {
        stage('build') {
            steps {
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh 'python3 -m venv venv'
                    sh '. venv/bin/activate'
                    sh 'pip install -r requirements.txt --user'
                }
            }
        }
        stage('tests') {
            steps {
                withEnv(["HOME=${env.WORKSPACE}"]) {
                    sh '. venv/bin/activate'
                    sh 'ls'
                    sh 'python -m pytest -v --cov=calculator'
                }
            }
        }
    }
}
