pipeline {

    agent any
    
    environment {
        MAX = 100
    }
    
    parameters {
        string(name: 'NAMEOFBRANCH', defaultValue: 'develop', description: 'Branch to build')
        choice(name: 'ENVIRONMENT', choices:['LOCAL', 'DEVELOPMENT', 'RECETTE', 'INTEGRATION', 'PRODUCTION'], description: 'Environement to deploy')
    }

    stages {
        stage('Build') {
            steps {
                echo "You want to build the *${params.NAMEOFBRANCH}* branch"
            }
        }

        stage('Test') {
            steps {
                echo 'The test began ...'
            }
        }

        stage('Deploy') {
            when {
                expression {
                    params.ENVIRONMENT == 'LOCAL'
                }
            }
            steps {
                echo 'My environment deploy is LOCAL'
                echo "$MAX"
            }
        }
    }
}

