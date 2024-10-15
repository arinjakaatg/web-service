pipeline {

    agent any
    
    environment {
        MAX = 100
    }
    
    parameters {
        string(name: 'NameOfBuild', defaultValue: 'Alphorm', description: 'This is a name of your build')
        choice(name: 'EnvironmentDeploy', choices:['Local', 'Development', 'Recette'], description: 'Your Choice')
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
                    params.EnvironmentDeploy == 'Local'
                }
            }
            steps {
                echo 'My environment deploy is LOCAL'
                echo "$MAX"
            }
        }
    }
}

