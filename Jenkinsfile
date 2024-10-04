pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # Initialize conda
                source /opt/anaconda3/etc/profile.d/conda.sh
                conda init bash

                # Activate the environment and run pytest
                conda activate myenv
                pytest --maxfail=1 --disable-warnings

                echo 'pytest completed successfully'
                # exit 1 # Commented out since pytest will be run successfully
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
