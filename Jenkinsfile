pipeline {
    agent { docker { image 'python:3.6.6' } }
    stages {
        stage('build') {
            steps {
                sh 'echo $HOME'
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install -r requirements.txt --user'
            }
        }
        stage('tests') {
            steps {
                sh '. venv/bin/activate'
                sh 'flake8 --exclude=venv* --statistics'
                sh 'pytest -v --cov=calculator'
            }
        }
    }
}
