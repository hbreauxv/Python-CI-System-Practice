pipeline {
    agent { docker { image 'python:3.6.6' } }
    stages {
        stage('build') {
            steps {
                python3 -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
            }
        }
        stage('tests') {
            steps {
                . venv/bin/activate
                flake8 --exclude=venv* --statistics
                pytest -v --cov=calculator
            }
        }
    }
}