pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                sudo conda create -n mlip python pytest numpy pandas scikit-learn -c conda-forge
                sudo conda activate mlip
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # Activate the environment and run pytest
                sudo conda run -n mlip pytest
                pytest --maxfail=1 --disable-warnings || { echo "Pytest failed"; exit 1; }

                echo 'pytest completed successfully'
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
