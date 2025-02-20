pipeline {
    agent any 

    stages {
        stage('Restore') {
            steps {
                // Restore NuGet packages
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the project
                script {
                    bat 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests
                script {
                    bat 'dotnet test'
                }
            }
        }
    }
}
