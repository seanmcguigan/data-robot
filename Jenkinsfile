    pipeline {
    agent any

    environment {
        USER_CREDS = credentials('seanmc_user_creds')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "On branch $env.BRANCH_NAME"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
