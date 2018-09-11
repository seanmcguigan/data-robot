    pipeline {
    agent any

    environment {
        USER_CREDS = credentials('seanmc_user_creds')
    }

    stages {
        stage('Build') {
            steps {
                sh """
                echo 'Building..'
                echo "On branch $env.BRANCH_NAME"
                echo "With build number $env.BUILD_NUMBER"
                echo "With build id $env.BUILD_ID"
                echo "With node name $env.NODE_NAME"

                """
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
