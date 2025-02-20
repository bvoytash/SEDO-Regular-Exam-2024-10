pipeline {
    agent any 

    stages {
        stage('Restore') {
            steps {
                // Restore NuGet packages
                script {
                    sh 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the project
                script {
                    sh 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests
                script {
                    sh 'dotnet test'
                }
            }
        }
    }
}
