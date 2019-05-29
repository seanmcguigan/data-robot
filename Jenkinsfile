pipeline {
    agent {label 'slaveOne'}
    
    parameters {
        string(defaultValue: '', description: 'What environment?', name: 'Environment')
        choice(choices: ['eu-west-1', 'eu-west-2'], description: 'What AWS region?', name: 'region')
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
                echo "echo ${params.region}"

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
