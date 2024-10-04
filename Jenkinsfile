pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                sudo python -m venv env
                sudo source env/bin/activate
                sudo pip install pytest numpy pandas scikit-learn
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'
                pytest
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
