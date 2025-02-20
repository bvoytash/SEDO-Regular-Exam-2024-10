pipeline {
    agent any 
    tools {
        dotnet 'dotnet-sdk' // Refer to the name configured in the previous step
    }

    stages {
        stage('Restore') {
            steps {
                script {
                    sh 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'dotnet test'
                }
            }
        }
    }
}
