pipeline {

    agent any
    
    environment {
        MAX = 100
    }
    
    parameters {
        string(name: 'NameOfBuild', defaultValue: 'Alphorm', description: 'This is a name of your build')
        choice(name: 'ENVIRONMENT', choices:['LOCAL', 'DEVELOPMENT', 'RECETTE', 'INTEGRATION', 'PRODUCTION'], description: 'Choice your environement')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
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

