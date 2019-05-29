pipeline {
    agent any//{label 'slaveOne'}
    
    parameters {
        booleanParam(defaultValue: true, description: '', name: 'userFlag')
    }

    environment {
//        USER_CREDS = credentials('seanmc_user_creds')
        MY_FOO = "foo"
        HASH = sh(script: 'git rev-parse --short HEAD', returnStdout: true).trim()
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
                echo "With git hash $env.HASH"

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
