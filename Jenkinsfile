pipeline {
    agent any

    stages {

        stage('Build') {
            when {
                branch 'main'
            }
            steps {
                echo "Running FULL BUILD on MAIN branch"
                sh 'echo Building the application...'
            }
        }

        stage('Test') {
            steps {
                echo "Running tests on ${env.BRANCH_NAME}"
                sh 'echo Executing tests...'
            }
        }

        stage('Scan (DEV Only)') {
            when {
                branch 'dev'
            }
            steps {
                echo "Running code scan ONLY on DEV branch"
                sh 'echo Running SonarQube scan...'
            }
        }

        stage('Full Scan & Deploy (MAIN Only)') {
            when {
                branch 'main'
            }
            steps {
                echo "Running FULL scan + deploy for MAIN branch"
                sh 'echo Full SonarQube scan for MAIN...'
                sh 'echo Deploy step executing...'
            }
        }
    }
}

