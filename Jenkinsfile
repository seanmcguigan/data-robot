pipeline {
    agent any

    parameters {
        booleanParam(defaultValue: true, description: '', name: 'userFlag')
    }

    environment {
        USER_CREDS = credentials('seanmc_user_creds')
        MY_FOO = "foo"

    }

    stages {
        stage('Build') {
            steps {
                
                echo "flag: ${params.userFlag}"
                
                sh """
                echo 'Building..'
                echo "On branch $env.BRANCH_NAME"
                echo "With build number $env.BUILD_NUMBER"
                echo "With build id $env.BUILD_ID"
                echo "With node name $env.NODE_NAME"
                echo "With my foo $env.MY_FOO"

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
